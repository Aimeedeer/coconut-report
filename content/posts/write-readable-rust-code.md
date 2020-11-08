---
date: 2020-10-16
title: "Piece by Piece: Write Readable Rust Code"
---

I am a newbie programmer,
and this is my first post about my Rust programming experience.
Even though I have been involved in the Rust community for a while,
I am not familiar with programming in Rust.
I do want to have Rust in my toolkit though,
so I decided to get hands on and write some code.

As I started, 
I quickly learned some techniques to create more readable code.
I take notes and comment my code to remember better,
and help others learn from my experience.
Meanwhile, it's quite an efficient way to prepare documentation
for this project in the future.

In this post,
I use my toy blockchain codebase as examples.
You will see the code I originally wrote
and the final, improved code.


## Naming Expressions

In this piece of code, I put the parameters' values directly.
I thought it was convenient because of fewer lines of code.

```rust
let new_block = Block::new("01232123", "something")?;
```

But it's not obvious to readers what the parameters mean.
They are just strings.
Readers don't know the purpose of the parameters.

To make this code more clear,
we give each parameter a name, showing its meaning.
Now the code looks like below:

```rust
let prev_hash = "000001232123";
let block_data = "something";

let new_block = Block::new(prev_hash, block_data)?;
```

Having every parameter on its own line with its own name
makes the intent more clear.
Now we know that the `Block::new` function
requires parameters for `prev_hash` and `block_data`.

Pretty straightforward, isn't it?

## Variable Shadowing

Variable shadowing, or name shadowing,
happens when a variable becomes inaccessible because
a new variable with the same name has been defined
in the same scope.

There are different opinions on name shadowing.
Some think it's confusing,
some think it makes code clean to reuse the same name for intermediate values.
I don't have enough experience to judge it yet, 
but I am pretty happy with name shadowing in this example.
Take a look at [variable shadowing examples in multiple languages](https://en.wikipedia.org/wiki/Variable_shadowing)
if you want to dig more.

In the example below, I defined each variable for one-time use
(pay attention to the **code comments**):

```rust
impl Block {
    pub fn new(prev_hash: String, block_data: String) -> Result<Block> {
	let new_timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

        // Define `new_hash`
	let mut new_hash = Sha256::new();
	
	new_hash.input(&serialize(
	    &(&block_data, &new_timestamp)
	)?);

	// Define `hash_result`
	// for taking value of `new_hash`'s output.
	let hash_result = new_hash.result_str();
	// `new_hash` is no longer useful 

	let block = Block {
	    timestamp: new_timestamp,
	    prev_block_hash: prev_hash,
	    hash: hash_result,
	    block_data: block_data,
	};

	Ok(block)
    }
}
```

Then we use the variable shadowing and
the code turns out to be this:

```rust
impl Block {
    pub fn new(prev_hash: String, block_data: String) -> Result<Block> {
	let new_timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

	// Define `new_hash`
	let mut new_hash = Sha256::new();
	
	new_hash.input(&serialize(
	    &(&block_data, &new_timestamp)
	)?);

	// Redefine `new_hash` --
	// we no longer need the previous `new_hash`
	let new_hash = new_hash.result_str();

	let block = Block {
	    timestamp: new_timestamp,
	    prev_block_hash: prev_hash,
	    hash: new_hash,
	    block_data: block_data,
	};

	Ok(block)
    }
}
```
We shadow variable `new_hash` by redefining it for a new value,
with a different type.
The new `new_hash` points to another memory location where
the `.result_str()` output stored.

This might not be the strongest example of where
to use variable shadowing.
Rust book explains better in [**Scope and Shadowing**](https://doc.rust-lang.org/rust-by-example/variable_bindings/scope.html#scope-and-shadowing)
and gives another example with variables in different scopes.


## Field Init Shorthand

Rust has special struct initialization syntax that allows 
[**Using the Field Init Shorthand when Variables and Fields Have the Same Name**](https://doc.rust-lang.org/book/ch05-01-defining-structs.html#using-the-field-init-shorthand-when-variables-and-fields-have-the-same-name).

We can make the previous code even better:

```rust
impl Block {

    // Give parameters the same names as `Block` fields
    pub fn new(prev_block_hash: String, block_data: String) -> Result<Block> {

    	// Define `timestamp` variable 
	// with the same name as `Block` field `timestamp`
    	let timestamp = SystemTime::now()
		.duration_since(SystemTime::UNIX_EPOCH)?
		.as_millis(); 

	// Define `hash` variable
	// with the same name as `Block` field `hash`
	let mut hash = Sha256::new();
	
	hash.input(&serialize(
	    &(&block_data, &timestamp)
	)?);

	let hash = hash.result_str();

	// At the same time,
	// our block init can be much cleaner
	let block = Block {
	    hash,
	    timestamp,
	    prev_block_hash,
	    block_data,
	};

	Ok(block)
    }
}
```

We give variables and parameters the same names
as the `Block` struct fields in order to avoid repetition.
Now the `Block` init code looks a bit cleaner.

Doesn't it look cool?
