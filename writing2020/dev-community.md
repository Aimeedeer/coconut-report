## **Thoughts on developer community building**


*The experience of building developer community for Nervos CKB*


This is a post about my experiences and observations building community for [Nervos CKB](https://www.nervos.org) over the past year. In it I recap efforts we have done on developer engagement, feedback from developers, my thoughts based on previous experience, communication, and observation of different developer communities. It does not make any recommendations, but I hope it encourages thought and discussion. It is mostly aimed at those in the Nervos CKB community, but maybe it can inspire others who are building developer communities as well.

One on one conversations with my friends [Jane][jane-twitter], [Brian][brson-site], [Matt][matt-twitter], [Toya][toya-twitter], and Mike gave me a lot of inputs and helped me with these thoughts. Thanks to my friends, I appreciate having you!

In the text below, “I” refers to myself, and “we” refers to Nervos marketing team and me. Opinions and perspectives in this post are my own, not those of the Nervos team.

The source file [is on GitHub](todo), if you find incorrect information, please open an issue, or comment to this post directly. Thanks in advance.


## Brief recap of Nervos developer relations efforts

[Nervos](https://www.nervos.org/) participated in the Rust community and open source community because its base layer, [CKB](https://www.nervos.org/ckb/), is [an open source project](https://github.com/nervosnetwork) written in the Rust programming language.

We sponsored [RustFest Rome](https://rome.rustfest.eu/), [RustFest Barcelona](https://barcelona.rustfest.eu/) and [Rust Tokyo](https://rust.tokyo/).

We organized [RustCon Asia 2019](https://rustcon.asia/), which is the first Rust community conference in Asia. I wrote an article about it, [A Close Encounter with Rust Community](https://aimeedeer.com/2019/04/29/a-close-encounter-with-rust-community/).

I started the development of the [RiB Newsletter][rib-site], which aims to create community and spread knowledge between Rust blockchain projects.

We started to organize Rust in Blockchain events in SF, Berlin and Hangzhou, China in 2019 as a way of supporting CKB, and integrating the project with the broader Rust blockchain community. Thanks to Jane for making it happen!

We sponsored the China Open Source conference -- COSCon’18 and COSCon’19, to support open source in China.

We sponsored [Ruby China](https://ruby-china.org/) because many CKB developers have connections with the Ruby community. Thanks to [Daniel Lv](https://twitter.com/lgn21st), who has been running and maintaining Ruby China for more than ten years, and connected the Nervos team with talented developers.

Other than that, there are many excellent blockchain tech conferences such as Berlin blockchain week, SF blockchain week, Osaka blockchain week, Shanghai blockchain week, and more. Most of those blockchain weeks include several high quality keynotes, workshops, and hackathons. If you are interested in blockchain development, you should attend at least one.

Aside from those marketing-like activities, the developers also gave talks and shared development knowledge with wider communities:

- [Tannr](https://twitter.com/TannrAllard) gave talks at the [Rust-in-blockchain](https://www.eventbrite.com/e/rust-in-blockchain-workshop-day-sfbw19-tickets-75088875849) workshop during SFBW, Nervos meetups during Berlin Blockchain Week, and he has been a judge on several blockchain hackathons.
- I gave the [Rust in China](https://github.com/brson/rust-in-china) talk with [Brian Anderson][brson-site], and a talk, [Build a VM in Rust that also runs Rust](https://rust-in-blockchain.github.io/rust-vm/), with him as well. Thanks to Brian for his efforts.
- [Xiao](https://xuejie.space/about/) gave talks at the first Rust-in-blockchain meetups (SF, Berlin), Web3 Summit, Nervos meetups and workshops.
- [Driftluo][driftluo-twitter] gave a talk at Rustcon Asia, [Implementing a p2p network framework (in Chinese)](https://www.youtube.com/watch?v=Sijf3KjM1gE).
- More talks in Chinese were given by developers in the team.

The CKB core developers started to share thoughts and the development experiments on exploring build on CKB after Nervos [CKB mainnet](https://medium.com/nervosnetwork/a-decentralized-mainnet-launch-for-nervos-ckb-9cb119d15540) running in October 2019:
-  [Jan](https://medium.com/@janhxie) is the brain of CKB architecture design, he might be the one who understands blockchain technology and its philosophy the most.
- [Xiao][xiao-twitter] is the author of CKB-VM, he is very productive and often shares his thoughts on his [blog][xiao-site].
- [Ian](https://twitter.com/doitian) is leading the CKB development, and though he rarely blogs recently, he shares his reading and good tools on his twitter every week. You can always find good things from his [website](https://blog.iany.me/). He also led the [CKB development update ](https://medium.com/nervosnetwork/nervos-ckb-development-update-28-5c85be7a599e).
- [JJY](https://justjjy.com/about) started to blog more about building Rust on CKB. Follow his steps and build your stuff on CKB.
- [Driftluo][driftluo-twitter] is the author of P2P for CKB, and he [blogs](https://www.driftluo.com/) in Chinese. He is very active in the Rust China community and mentors newcomers often.

Other developers are contributing to different China developer communities, either giving talks or blogging and sharing, providing dev support at hackathons.

If you are a developer who is interested in being involved in the next-generation of distributed systems, do not miss any chances to connect to those developers. You can always find them from the links above, or on [Nervos GitHub][nervos-ckb-github] easily.

To know more about Nervos CKB, it's good to start with reading docs on [Nervos doc][nervos-doc] and [Nervos Talk forum][nervos-talk].


## Challenges I’ve met on engaging developers

**Developers are not aware of Nervos.** For example, at RustFest, I met many developers and most had not heard of Nervos, but they know Parity and their developers.

**Developers follow developers, not marketers.** As a non-tech person, I can reach out and pitch, but it is interactions with existing developers that are most impactful to new developers.

**Messaging that does not reach developers.** As an example, of all the developers I have talked to, only one knew the grants plan. Some weren't familiar with what grants are and how they worked, unless they were familiar with blockchain communities. Some found the term, "grants RFC", confusing -- the language we used didn’t reach developers.

**Lack of constant call for participation.** Some developers know that Nervos is the top blockchain in China, but they don’t know they can participate in, or even contribute. This makes it hard to entice new contributors. Nervos CKB doesn’t consistently show the public that the project is open and willing to build an open source developer community. As an example, while CKB does have "good first issue" tags (great!), there is no ongoing effort to connect developers with these issues.

**New developer retention.** During the work for Nervos, I reached out to several developers from offline events or other online communities. I shared project chat channels, official forum, GitHub repos, official blog page. After that, I also tried to keep them posted by sharing CKB developers blog posts or some tech content with them. But the reality is, they left our project conversations and didn’t intend to follow updates -- they are not interested.

## Feedback from developers

Here is some of the feedback I've heard from developers:

- A Rust dev tried to understand CKB but failed, and he said it's hard.
- A WASM dev also tried to read CKB documentation but didn't have growing interests to check back.
- A senior Rust developer said he had read various CKB docs and never came away feeling like he understood the vision, or how it is implemented by the tech.
- A senior system programming developer, who planned to find a great startup to join in, paid much time to read CKB GitHub and then get a basic understanding. He finally decided not to join the team for different missions.
- A senior blockchain developer is interested in technology discussion with CKB developers but has no interest in CKB project. Sam as some other blockchain developers I have talked to.

Most developers have a rapid visit and leave; they don't find enough interesting at CKB if they don't pay enough time to dive in its documentation. That feedback makes me think and to ask questions -- what are the real problems that we didn’t notice, any signs we missed?


## Thoughts

There are huge numbers of blockchain projects for a limited number of blockchain developers to get involved with, so it is hard to get developers' attention. The [RiB Newsletter][rib-site] traffic data says something: in the last three months Nervos received less traffic than most other projects RiB covers.

Based on previous years of developer community building, I can see there are a lot of general developers who want to join projects. How to hook most developers quickly might be the biggest obstacle to getting developers -- it's not immediately obvious to newcomers why they should build on CKB.

What can we do to better approaching developers for Nervos CKB? How to show them the starting point, the entrance, and how to get onboard on CKB effortlessly? Or, I would like to ask questions in another way:

- What content (either articles or events) is understandable and welcomed by developers?
- What would make CKB worth developers' time for reading to understand, and maybe try to build?
- How long would it take from the first engagement to build on CKB?
- What exact things do developers need to achieve this goal -- building on CKB ecosystem?


## Examples from other communities

Let’s take a break to see what others did. I list some community-oriented features of other open source projects here, mostly ones that I or my friends are familiar with.

#### [Spacemesh](https://spacemesh.io/)

- The official website is very hacker style
- Project updates (and other content, jobs, etc) are quite clear
- Blog posts are insightful
- Graphics for blog posts are fresh and stylish
- Cool people: [Lane](https://github.com/lrettig) built EVM, [Avive](https://github.com/avive)  cares user experience very much
- The team page is special, memorable. Team members are listed there equally, which is different from most of the other projects' team page

#### [Parity](https://www.parity.io/)

- Massive content, focused on developers, videos and blog posts; developers can know what is the next step after watching or reading them
- The showcase event for developers: sub0.1 conference recorded 7 videos with different topics in January
- Includes community generated content: [Custom Solutions ](https://www.parity.io/tag/custom-solutions/) as part of [Parity blog](https://www.parity.io/blog/)
- [People of Parity](https://www.parity.io/tag/people-of-parity/) blog series
- GitHub clearly demonstrates a lot of activity, with developers engaging contributors (even Gavin Wood participates regularly).
- Core developers have their own brand and personalities: [libp2p](https://github.com/libp2p), [are we web yet](https://www.arewewebyet.org/), [ZK podcast](https://www.zeroknowledge.fm/), and more
- Core developers do dev advocating as well as community advocates

#### [NEAR](https://nearprotocol.com/)

- Co-founders and core developers do advocate frequently
- Rust in Blockchain workshop, meetup, and more
- China tour meetups
- [Whiteboard Series with NEAR](https://www.youtube.com/results?search_query=%23WhiteboardSeries), the tech educational interview

#### [PingCAP](https://pingcap.com/)

- Keep building and maintaining Chinese content channels: [Zhihu](https://zhuanlan.zhihu.com/newsql), wechat official channel, etc
- Educational channel [PingCAP University (in Chinese)](https://university.pingcap.com/)
- Official community channel [PingCAP Community(in Chinese)](https://pingcap.com/community-cn/) with events and learning resources
- Official [blog in Chinese](https://pingcap.com/blog-cn/) and [blog in English](https://pingcap.com/blog/), and the English blog posts got high votes on Hacker News often
- Co-founder and core developers are active in maintaining their company on the Quora-like community platform: [PingCAP 这家公司的前景如何？
](https://www.zhihu.com/question/64878683)
- Word of mouth [example](https://twitter.com/xgsun/status/1227988509358604288?s=19)

#### [Mozilla Firefox](https://www.mozilla.org/en-US/firefox/)

- [Mission-oriented](https://www.mozilla.org/en-US/mission/). Mozilla appeals to developers with its principles of preserving an open internet and fighting for user privacy.
- Strong blog cadence. Mozilla cranks out blogs regularly, many with deep technical content that appeals to a wide developer audience. Note though that Mozilla's blogs are disorganized. Some examples:
- [Official blog](https://blog.mozilla.org/)
- [Mozilla hacks](https://hacks.mozilla.org/)
- [GFX team blog](https://mozillagfx.wordpress.com/)
- [VR blog](https://blog.mozvr.com/)
- [Servo blog](https://blog.servo.org/)
- [nnethercote](https://blog.mozilla.org/nnethercote/).
- Self-starting culture. Individual engineers tend to be motivated to spread successful open-source habits of mentoring, blogging, and personal brand-building. As evidenced by the proliferation of Mozilla blogs.

#### [Rust](https://www.rust-lang.org/)

- Strong product vision and market niche -- those aware of it can easily identify what is unique and important about it. It is conveyed relatively clearly on the website.
- Community-oriented structure and processes -- almost every initiative is designed for participation. Unpaid team members participate at the highest levels of the organization.
- Documentation-oriented culture and processes (new features cannot be added without documentation)
- Rust community has the [what's everyone working on this week](https://www.reddit.com/r/rust/comments/f541u0/whats_everyone_working_on_this_week_82020/) and yearly looking back & looking forward blogging call, which are the sense of ceremony in the community
- There are several newsletters made by the community: [this week in Rust](https://this-week-in-rust.org/), [Awesome Rust](https://rust.libhunt.com/), [Read Rust](https://readrust.net/), the [The Embedded Working Group
](https://rust-embedded.github.io/blog/), etc
- Regional Rust conferences around the world made by contributors


## A comparison: Nervos vs Parity blog content

As an experiment, I searched blog posts from Nervos and Parity official channels, to see the differences in content. For this experiment, I used blog posts from January 2019 until February 2020.

![](https://github.com/Aimeedeer/coconut-report/blob/master/graphic-assets/Nervos-online-content.svg)
![](https://github.com/Aimeedeer/coconut-report/blob/master/graphic-assets/Parity-online-content.svg)

The two charts show the content with their official tags, and how they define their content as a way of defining their audience. Nervos had 110 posts during this time period, and Parity had 44. I was surprised by this, as I didn't realize that there is such a big difference in the number when I search content for [RiB Newsletter][rib-site] each month.

There are clear differences in the categorization of content. Nervos has a few general categories. Parity has many specific categories, and Parity's categories are more technical. I think Nervos's categorization may have difficulties reaching the right audience.

With the projects categorizing their content differently, it is hard to compare them. To make a simpler comparison, I added the same tags to each project's posts: culture, tech, status report, marketing. So the charts turn out to be like this:

![](https://github.com/Aimeedeer/coconut-report/blob/master/graphic-assets/Nervos-online-content-with-my-tags.svg)
![](https://github.com/Aimeedeer/coconut-report/blob/master/graphic-assets/Parity-online-content-with-my-tags.png)

In this analysis, Parity has a higher percentage of technical and culture content than Nervos, compared to marketing content.

Date for these charts is in a [Google Sheet](https://docs.google.com/spreadsheets/d/1baIlM1x5tWeKkglZdawEZeRexQxq0cfMjaTM9fYRLzE/edit?usp=sharing).


## Stories that need to be told about Nervos

There are many ways to build community. The stories we tell about our project shape developers' opinions. When we tell a good story consistently then people will remember.

**Useful and essential information for developers**
        - Essential and must have documentation, each product should have an instruction book    
**Project mission**, inspiring and for public good
        - Why Common Knowledge Base
        - What's the value
        - Backed up with stories
        - Align with co-founders stories and their dreams        
**Engineering mission**, to show the insights from the engineering team: why Nervos CKB is the future, and what the future looks like
        - Software aspect, history of the internet, bitcoin stories, and other relative topics
        - Decentralized world
        - Distributed systems
        - Engineering efforts stories
        - The architecture of Nervos CKB
        - The possibility it provides to the world as well as to the developers
        - Stories that happened during CKB development    
**Engineering culture**,  to attract and onboard new developers
        - How developers work together
        - Stories about CKB developers
        - How the open source thoughts and efforts of building the open culture
        - Efforts about encouraging contributions
        - Developers’ sharing efforts: blog posts, talks, workshops
            - The enjoyment of working for Nervos CKB -- remote, flexible, etc  
**Tech awareness rising**, cool tech details that easy to understand by newcomers, which makes people remember
        - Why CKB-P2P but not libp2p?
        - Why RISC-V VM but not WASM VM?
        - Build xx on CKB-VM series -- find cool projects to build on CKB-VM
        - Cell model
                - The design thinking
                - Use cases proof
        - Credit contributions and the storytelling -- align with the missions, for the better society
        - Educational content and mentorship for the crypto tech community
                - An example: [A Gentle Introduction to Bitcoin Core Development](https://bitcointechtalk.com/a-gentle-introduction-to-bitcoin-core-development-fdc95eaee6b8), the step by step mentorship help new developers to make an action without pressure.
        - Inspiring movements -- creative hackathons, educational events and open sharing

We can tell these stories now. There are many more technical stories to tell that I don't know, and I think they are some of the most important. Developers follow developers.

## Conclusions

I hope some of this information is useful, and can inform our community building efforts.

Finally, I want to share this post on [Onboarding to Bitcoin Core](https://medium.com/@amitiu/onboarding-to-bitcoin-core-7c1a83b20365). It is a story of a great new-contributor experience. Can we provide the same?

As community builders, our primary purpose is to be friendly and open to newcomers, to open the possibilities for developers and encourage people to play around with CKB. To let developers see that they can create something great here.

I believe that happy contributors will be advocates later on. They will attract new developers, from Rust, open source, Ruby, Go, JS, Ethereum, Bitcoin, and other communities all around the world.

Keep moving, and keep advocating. CKB is cool. Let's all be cool.


[jane-twitter]: https://twitter.com/cryp_TOTO
[matt-twitter]: https://twitter.com/matt_bitcoin
[toya-twitter]: https://twitter.com/toya77196996
[brson-site]: https://brson.github.io/
[xiao-twitter]: https://twitter.com/xxuejie
[xiao-site]: https://xuejie.space/
[driftluo-twitter]: https://twitter.com/driftluo
[rib-site]: https://rustinblockchain.org/
[nervos-ckb-github]: https://github.com/nervosnetwork/ckb
[nervos-doc]: docs.nervos.org
[nervos-talk]: https://talk.nervos.org/
