---
layout: post
title: Decentralize What?
categories: [Identity, Decentralized]
---

We're almost ready for a definition of "decentralized identity", but only after unburdening ourselves of some baggage brought in with the word "identity". 

In this post (and this blog in general), the word "identity" almost always refers to your _digital_ identity. We'll distinguish this from <<Identity>> with a capital-I, which refers to other ways in which you may be thinking of this word, i.e., to describe the complex, multi-faceted, and beautiful person that you are 🤗, which can never be reduced to digital representations.

Digital identity includes ways you knowingly use it, and ways it is used without your knowledge or consent.

Examples:

- Accessing online services, such as logging into your account on a web site
- Being asked to provide proof of your attributes or state/government official documents, such as a driver's license
- Data aggregators building a profile of you based on your online activities

That escalated quickly. Let's focus on the first one, which seems straightforward. When you log into a web site, of course they need to know _who you are_, right? I.e., they need to know your <<Identity>>? 

Actually, in many cases they don't, but you are certainly accustomed to service providers requesting (or _already possessing_ through mysterious means) way more information about you than they need. 

For now, keep in mind that the word "identity" may set an unfortunate mental model (and acceptance) that you need to provide more information about who you are than is needed to obtain a service. Certainly in some cases, e.g., due to regulations, a lot needs to be known about you. In other cases, you are simply cowed into handing over bonus personal information, which turns out to be a profitable side hustle for your service providers.

> In fact, some identity experts are highlighting the need to shift away from "identity" and the baggage it brings along. The refreshingly blunt Steve Wilson declared ["Identity is Dead"](https://www.constellationr.com/blog-news/identity-dead), underscoring that online service providers rarely need to know _who you are_.

### Evolution of digital identity models

Decentralized identity is often presented as the next step in the evolution of digital identity models. To be concrete, think of logging into your account on a web site. In general, you're accustomed to logging in with your username and password. (Increasingly sites may require additional confirmation -- such as having you enter a confirmation code they emailed -- to avoid some security problems touched on below, but that doesn't affect this overview.)

##### Centralized identity

In the early days of the web, when sites looked like this...

<img src="/images/post-2021-12-10/amazon_1995.png" alt="amazon in 1995" width="400"/>

...and you browsed the web in your pleated, acid-washed jeans, you needed to create a different account for every web site you use. We refer to that as centralized identity.

<img src="/images/post-2021-12-10/centralized.jpg" alt="centralized model of identity" width="600"/>

In this model, each organization you interact with does the work of authenticating you (confirming you're the user they expect), which includes storing and securing your acccount login credentials. 

Each of these organizations further needs you to enter relevant personal data (your shipping address, for example), which they store along with any other data you generate while interacting with them -- usage activity and other artifacts. 

The end result is that your data, including information needed to verify your login credentials, is stored with every organization you interact with.

<img src="/images/post-2021-12-10/centralized_with_data.jpg" alt="centralized model of identity demonstrating your data" width="600"/>

> If you're worried about your data being everywhere, good. This data is vulnerable and it's constantly being breached. Note that this problem doesn't magically get fixed as we move up the  identity evolutionary spectrum. We'll come back to this later.

##### Federated identity

Because handling user authentication carries risk, not every organization wants to do it themselves. A way to offer increased security and convenience to users is through federated identity. In this model, identity providers authenticate you as a service to you and other organizations.

You know this very well from the "login with google", "login with facebook", etc buttons you've seen on some web sites. (FWIW, we call this the NASCAR view.)

<img src="/images/post-2021-12-10/federated.jpg" alt="federated model of identity" width="600"/>

But this means fewer organizations have your data, right? Only the identity provider has it? 

OF COURSE NOT my sweet summer child. On the one hand, these organizations may _need_ some items to transact with you, like your mailing address. But more importantly, everyone _wants_ your data, that pure digital gold. However, in this model, fewer people are managing securing your login credentials, which is a win.

<img src="/images/post-2021-12-10/federated_with_data.jpg" alt="federated model of identity demonstrating your data" width="600"/>

In sum, the benefits to you in this model are:
- Managing fewer logins
- Ideally these identity providers are better equipped to secure your login credentials

But oh what a fantastically complete view into all your online activities can be built with this model, as you are correlatable across all of these organizations and beyond. This data is extremely valuable to anyone that wants to advertise to you in a more targeted way, and this is sold, aggregated, repackaged, shipped around everywhere.

On the other hand, very little of this data proliferation actually manifests as convenience to _you_. Companies that control especially valuable data silos are extremely protective of these gold mines and generally have no incentive to make it easy for you to leave their platform for another.

##### Decentralized identity

Then we get to decentralized identity. At this point in a decentralized identity presentation, you would be told that decentralized identity is intended to fix some of the problems described above. (Suspend disbelief for a minute.)

On offer:

- Portable data you control
- Your consent is required before your data is used/shared
- Service providers only obtain the information they need to transact with you.

In the deccentralized identity model, you interact directly with peers, which includes service providers/organizations from the previous diagrams. (Note the shift in power -- in fact you can mutually authenticate.)

<img  src="/images/post-2021-12-10/decentralized.jpg" alt="decentralized" width="600"/>

In this model, distributed ledgers are often used to anchor data that assists in verification and generally establishing trust. But note that personal data is never stored on-chain, or rather, it shouldn't be. We'll come back to this in much greater detail.

So anyway, decentralized identity solves all of your problems through the magic of blockchain and cryptography, and so you switch to this model and your identity is fully decentralized, no one has a copy but you, and we're done. 😌

No. Sadly, after all that, decentralized identity models do little on their own. 

Service providers may keep a copy of your data, and they may sell it to others. This fancy bit of tech has can't disrupt the data broker industrial complex overnight. So where does this leave us? 

### Back to the real world

The above was a straw man argument, but that was intentional. The fact is that many representations of decentralized identity (or self-sovereign identity) focus on purely technical solutions to complex problems, scaring away potential partners whose perspective is critical to achieving the _goals_ of decentralized identity. I've seen this in education, for example, with experts assuming decentralized identity must be incompatible with educational regulations, such as FERPA in the USA.

This is a good reminder of the limitations of what a technical solution _on its own_ can accomplish, and the nuances of applying decentralized identity architectures, standards, and technologies to the real world. 

In practice, while decentralized identity tech may improve some of the problems described above, we still require regulatory frameworks (such as the GDPR) to nudge service providers to obtain your consent to use your data, allow you visibility into data collected about you, etc.

Also keep in mind that sometimes organizations are required to keep data about you (e.g., for compliance with financial regulations). And so the representation that, with decentralized identity, no one but you will have a copy of your data is not realistic.

### Broadening our view, and a definition

With this reminder, the goals of decentralized identity require a much more comprehensive approach. For now, we'll use the following definition to try to capture where the goals of decentralized identity cannot be achieved through tech alone:

> Decentralized identity: a set of technical standards and principles seeking to enable a shift toward more individual control over digital identities and personal data.


### Advantages and Opportunities

Decentralized id standards do help with some things right away, but other things require a longer view. 

Immediately, decentralized identity standards are useful for making your data more portable. You can take your work, education, financial (such as accredited investor status), and other credentials with you, sharing them with others who can independently verify they are authentic and tamper-proof -- without needing to cntact the issuer. This aspect can offer immediate efficiencies and ease of access.

In the longer view, we need to consider possibilities unlocked by this new architecture. And this is the exciting part, which won't happen overnight. 

And this would be a good cliff hanger, so bye!
