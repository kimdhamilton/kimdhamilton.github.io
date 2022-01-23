---
layout: post
title: Speaking of Decentralized Identity...
categories: [Identity, Decentralized]
---

Decentralized Identity is popping up in exciting places!

- Square's [tbDEX white paper](https://tbdex.io/whitepaper.pdf) describes a protocol enabling direct negotiation of trust between peers. Its goal is increasing the ability for _real_ people to use cryptocurrency, "utilizing decentralized identity and verifiable credentials" to establish provenance of real-world identity. 
- Spruce has developed [Log in with Ethereum](https://blog.spruceid.com/sign-in-with-ethereum/), based on its decentralized identity toolset, which allows users to access web services with their ethereum accounts (instead of the typical need to create accounts with multiple providers), enabling a more seamless web experience.
	
Is it finally happening for this decades-long labor of love, previously confined to dusty corners of standards groups and austere conference rooms? Is it ready? Is it overdue? 

Oh, and what ... _is_ it?

If you were in a decentralized identity talk right now, you'd 95% likely see this slide 

<img style="border:1px solid black;" src="/images/post-2021-12-08/internet_dog.jpg" alt="on the internet no one knows you're a dog" width="600"/>

There's usually forced laughter at this point, which has bothered me over time because I've never felt like this is a good framing for "identity problems" on the web. This confusing frame of reference is followed by the problem statement behind dogs-on-the-internet "The problem is that the web doesn't have an identity layer...". And then comes an absolute battering by acronyms and counterfactual web-with-identity diagrams, all claiming to solve this problem you're not sure you understood in the first place. (Please note: this is a self-criticism as much as anything, as you'll see below.)

Either that or grandiose claims that should make you skeptical. It doesn't help that the standards, technologies, and principles of decentralized identity are sometimes referred to more reverently as "self-sovereign identity".

There was a reason I wrote this:

<img src="/images/post-2021-12-08/cult1.png" alt="I just want to verify a credential; I don't want to join a cult" width="600"/>

I wrote that offhandedly/jokingly as a criticism of our collective inability to adequately describe the value-add for individuals. But I knew I was on to something when I immediately got DMd by ~15 different colleagues over a variety of encrypted channels demanding to know "exactly who were you subtweeting, was it X person/company/technology?". 

A more introspective chap texted "you were talking about me, right?", and I admire that.

Then there were replies like this:

<img src="/images/post-2021-12-08/cult2.png" alt="such a cult" width="600"/>

And jokes (jokes, right?) that I'm actually the cult leader so of course I don't need to join it. I swear this wasn't a directed subtweet, but the response was clear -- people definitely perceived cults or cult adjacencies that were worth exploring.

"Decentralized identity" is an incredibly complicated catch-all term that takes a while to unpack and understand. I've been _trying_ to explain it for years, tweaking definitions and analogies to hopefully make it understandable to humans and explain why it's useful. 

My lens/focus has been building decentralized identity systems with the elements that are "ready-to-use", which is of course subjective but is my best attempt to derisk based on the following considerations:

- Maturity of standards and technologies
- Availability of open-source implementations
- Minimizing risk to users of these systems, which is especially critical when introducing new tech/systems _about identity data_ into people's lives. This includes considerations of lockin, threats to privacy and agency, and risk of loss
- System availability, resilience
- Ability to integrate into the systems already in use
- Usability 
- And dammit why is usability last on the list when it's central to almost all of the above and one of the most important factors.

A specific focus was systems and schemas supporting formal and informal credentials representing learning, work, and skills. As important as (if not more than) the work of building is the work of communicating, a challenge I've thrown myself into excitedly, if awkwardly.

More recently, applying it to a new domain of DeFi, I've been picking through my previous decks and docs to try to curate the most useful explanations for my colleagues, and decided I should try sharing them more broadly.

In this series, I wanted to talk informally about decentralized identity in various forms -- metaphors, pitfalls, myths vs facts, with the goal of helping you navigate and detangle this often confusing space, but also to explain how and why _I_ think it some elements can help address very real risks of how your personal data is handled. 