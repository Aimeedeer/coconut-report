---
date: 2020-11-15
title: "Test and Open An Issue"
categories: ["programming"]
tags: ["issue", "test", "utterances"]
---

A couple days ago, I wanted to share a Rust blockchain-related video 
to the [rib.rs learning page](https://rustinblockchain.org/learning)
by posting a comment there.
Then suddenly I found out something was wrong --
it didn't show my posted comment at all!
I tried again, but nothing happened.

I remembered it worked before in previous newsletters.
Did I change any code by mistake when I pushed the last newsletter?
I don't see it from the git log.
I tried on other pages, and it still didn't work.
Then I tried on my personal blog site, which uses the same plugin.
It was weird that it only worked on one blog post but
not other pages.
It doesn't make sense to me. I was perplexed.


## Record Down All Tests

I use [Utterances](https://github.com/utterance/utterances)
as the Hugo commenting plugin.
It creates an issue on your public GitHub repo
if someone comments on your website.
The plugin is put in a template HTML file
used in each article page, and it is
supposed to work exactly the same way.

I made a second round of tests with my already published website
and then tested it locally. I commented on
- [a blog post](https://impl.dev/posts/write-readable-rust-code/), and it worked with my test message
  (which I have deleted already);
- [another blog post](https://impl.dev/posts/2020-05-10-notes-on-rules-of-thumb/), and nothing happened;
- [a third blog post](https://impl.dev/reports/2020-09-27/) , and
  nothing happened.

After that, I couldn't understand why it worked on the first
blog-post test.
Then I wanted a safe testing environment without
destroying my original website code or content.

## Build A Clean Environment for Test

I created a one-page website that only contains Utterances.

```html
<!DOCTYPE html>
<head>
  <title>Test Utterances</title>
</head>
<P>Test Utterances</p>

<script src="https://utteranc.es/client.js"
        repo="Aimeedeer/test-utterances-bot"
        issue-term="title"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
```

The repo is [here](https://github.com/Aimeedeer/test-utterances-bot),
and the published page is
[Test Utterances](https://aimeedeer.github.io/test-utterances-bot/).
Since then, I can bravely try anything with this page.


## Find and Report the Issue

I opened the browser inspecter to see request activities
from the console.
I use Brave by default and sometimes use Firefox.	

The browser console showed me one or two failures.
Some appeared in previous
[Utterances issues](https://github.com/utterance/utterances/issues)
-- official issues are helpful
-- but were unrelated to my case.

My testing diagnosed a 403 request issue,
and I couldn't solve it on my own.
So I reported to Utterances official, expecting they can help.
My issue is:
[HTTP/2 403 Forbidden when posting comment](https://github.com/utterance/utterances/issues/418).

By reporting the issue,
I learned how to write an instant-understandable title,
provide an isolated environment for others to test,
and an accurate description with error messages.

To my surprise, the issue got upvotes and was fixed very soon.
I love actively maintained products, and I think I helped.
It's interesting to see other people tested on my site too. Cute!
