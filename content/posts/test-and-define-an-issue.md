---
date: 2020-11-08
title: "Test and Define An Issue"
---

Report A Bug

A couple days ago, I wanted to share a Rust blockchain-related video 
to rib.rs learning page by commenting on it (1 second lazy).
Then suddenly found out something got wrong --
it didn't show my posted comment at all.
I tried again, but nothing happened.

I remembered it worked before in previous newsletters.
Did I change any code by mistake when I pushed the last newsletter?
But I don't see it from the git log.

I tried on other pages, and it still didn't work.
Then I tried on my blog site, which uses the same plugin.
It was weird that it only worked on one blog post but
not other pages.
It doesn't make sense to me. I was perplexed.


## Record Down All Tests

I use [Utterances](https://github.com/utterance/utterances)
as the Hugo commenting plugin.
It creates an issue on your public GitHub repo
if someone comments on your website.
The plugin is put in a template Html file
used in each article page, and it is
supposed to work exactly the same way.

I tested the second round
that started from my already published website
and then local testing. I commented on
- [a blog post](https://impl.dev/posts/write-readable-rust-code/), and it worked with my test message
  (which I have deleted already), and it worked;
- [another blog post](https://impl.dev/posts/2020-05-10-notes-on-rules-of-thumb/), and nothing happened;
- [a third blog post](https://impl.dev/reports/2020-09-27/) , and
  nothing happened.

After that, I couldn't understand why it worked on the first blog-posttest. Then I want a safe testing environment without
destroying my origin website code or content.

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

I opened browser inspect to see request activities from the console.
To be clear, I use Brave as default and sometimes use Firefox.	

The browser console showed me one or two failures,
and they were shown on previous
[Utterances issues](https://github.com/utterance/utterances/issues)
-- official issues are helpful
-- which are not my case.

My test diagnosed a 403 request issue,
and I couldn't solve it on my own.
So I reported to Utterances official, expecting they can help.
My issue track is:
[HTTP/2 403 Forbidden when posting comment](https://github.com/utterance/utterances/issues/418).

By reporting the issue,
I learned how to write an instant-understandable title,
provide an isolated environment for others to test,
and an accurate description with error messages.

To my surprising, the issue got upvotes and was fixed very soon.
I love actively maintained products, and I think I helped.
It's interesting to see other people tested on my site too. Cute!
