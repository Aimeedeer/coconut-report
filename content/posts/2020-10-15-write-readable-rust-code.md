---
date: 2020-10-15
title: "Piece by Piece: Write Readable Rust Code"
---

I began to program a blockchain in Rust from scratch recently,
and slowly take notes piece by piece
-- taking notes always help memorizing knowledge.

You will see the original lousy piece of code and 
the improved more readable piece.

## Statements Claiming

In this piece of code, I put the parameters' value directly.
I thought it was convenient because of fewer lines of code.

```
let new_block = block::Block::new(
	"01232123".to_string(),
	"newdata".to_string())?;
```

But it's not obvious to readers that
what exact data that `block::Block::new` needs.
Readers can only see the parameter's type, `String`,
without knowing what value is needed to create a new `Block`.

Concerning that,
we gave each parameter a name, showing its meaning.
Now the code turns to be below.

```
let prev_hash = "000001232123".to_string();
let data = "newdata".to_string();

let new_block = block::Block::new(prev_hash, data)?;
```

When naming a variable,
the `let` statement gives each variable a new line
and, hopefully, an exact name as well.

Now we know that the `block::Block::new` function
requires two parameters, which are
the previous hash string, `prev_hash`, and the data string, `data`.

Pretty straightforward, isn't it?

## Variable Shadowing

Variable shadowing, or name shadowing, or name masking,
happens when a variable is "shadowed" by
be claimed with the same name in a new scope.

There are different opinions on name shadowing.
Some think it's confusing,
some think it makes code clean by reusing the same name. 
I don't have enough experience to judge it yet, 
and I am pretty happy with name shadowing in this example.
Take a look at [variable shadowing examples in multiple languages](https://en.wikipedia.org/wiki/Variable_shadowing)
if you want to dig more.

In the example below, I claimed each variable for one-time use
(pay attention to the **code comments**):

```
impl Block {
    pub fn new(prev_hash: String, data: String) -> Result<Block> {
	let new_timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

        // Claim `new_hash`
	let mut new_hash = Sha256::new();
	
	new_hash.input(&serialize(
	    &(&data, &new_timestamp)
	)?);

	// Claim `hash_result`
	// for taking value of `new_hash`'s output.
	let hash_result = new_hash.result_str();
	// `new_hash` is no longer useful 

	let block = Block {
	    timestamp: new_timestamp,
	    prev_block_hash: prev_hash,
	    hash: hash_result,
	    data: data,
	};

	Ok(block)
    }
}
```

Then we use the variable shadowing and
the code turns out to be this:

```
impl Block {
    pub fn new(prev_hash: String, data: String) -> Result<Block> {
	let new_timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

	// Claim `new_hash`
	let mut new_hash = Sha256::new();
	
	new_hash.input(&serialize(
	    &(&data, &new_timestamp)
	)?);

	// Claim `new_hash` for the second time
	let new_hash = new_hash.result_str();

	let block = Block {
	    timestamp: new_timestamp,
	    prev_block_hash: prev_hash,
	    hash: new_hash,
	    data: data,
	};

	Ok(block)
    }
}
```
We shadowed variable `new_hash` by claiming it again
but for a new value.
The new `new_hash` points to another memory field where
the `.result_str()` output stored.

Rust describes [**Scope and Shadowing**](https://doc.rust-lang.org/rust-by-example/variable_bindings/scope.html#scope-and-shadowing)
and gives another example with variables in different scopes.


## Field Init Shorthand

There is still space to make the code better.
We made more changes:

```
impl Block {

    // Give parameters the same names as the `Block` fields
    pub fn new(prev_block_hash: String, data: String) -> Result<Block> {

    	// Claim `timestamp` variable 
	// the same as `timestamp` in the `Block`
    	let timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

	// Claim `hash` variable
	// the same as `hash` in the `Block`
	let mut hash = Sha256::new();
	
	hash.input(&serialize(
	    &(&data, &timestamp)
	)?);

	let hash = hash.result_str();

	// At the same time,
	// our block init can be much cleaner
	let block = Block {
	    hash,
	    timestamp,
	    prev_block_hash,
	    data,
	};

	Ok(block)
    }
}
```

Rust allows 
[**Using the Field Init Shorthand when Variables and Fields Have the Same Name**](https://doc.rust-lang.org/book/ch05-01-defining-structs.html#using-the-field-init-shorthand-when-variables-and-fields-have-the-same-name).

We gave variables and parameters the same names
as the `Block` struct fields in order to avoid repetition.
Now the Block init code looks much shorter.

Does it look cool?
