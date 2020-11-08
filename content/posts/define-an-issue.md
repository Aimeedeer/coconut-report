---
date: 2020-11-08
title: "Test and Define An Issue"
---

Report A Bug

A couple days ago, I wanted to share a Rust blockchain related video 
to rib.rs learning page by commenting to it (1 second lazy).
Then suddenly found out something got wrong,
it didn't show my posted comment at all.
I tried again but nothing happend.

I remembered it worked before in previous newsletters.
Did I change any code by mistake when pushed the last newsletter?
But I don't see it from the git log.

I tried on other pages, and it still didn't work.
Then I tried on my blog site which uses the same plugin.
It was wired that it only worked on one blog post but
not other pages.
It doesn't make sense to me. I was totally confused.


## Record Down All Tests

I use [Utterances](https://github.com/utterance/utterances)
as the hugo commenting plugin.
It creates an issue on your public GitHub repo if
someone comments on your website.
The plugin is put in a template html file that is used 
in each single article page,
and it supposes to work exactly the same way.

I tested the second round,
that started from my already published website
and then local testing. I commented on
- [a blog post](https://impl.dev/posts/write-readable-rust-code/), and it worked with my test message
  (which I have deleted already), and it worked;
- [another blog post](https://impl.dev/posts/2020-05-10-notes-on-rules-of-thumb/), and nothing happened;
- [a third blog post](https://impl.dev/reports/2020-09-27/) , and
  nothing happened.

After that, I couldn't understand why it worked on the first blog post
test. Then I want to a safe testing enviroment without
destroying my origin website code or content.

## Build a Clean Test Enviroment

I created a one-page website that only contains Utterances.

```html
<!DOCTYPE html>
<head>
  <title> Test Utterances </title>
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
Now I can bravely try anything here.

I opened browser inspect to see request activies from the console.
To be clear, I use Brave as default, and sometimes use Firefox.	





## Open An Issue

[issue track: HTTP/2 403 Forbidden when posting comment](https://github.com/utterance/utterances/issues/418)
