---
layout: post
title: The Privacy Americans Are About to Lose
categories:
  - Driver's License
  - Privacy

---
<br>
*Part 3 of a series on Mobile Driver's License privacy. See part 2: [Is Server Retrieval Actually Optional? The Investigation That Revealed More Problems](../server_retrieval)*

## **The Last Refuge of Accidental Privacy**

In the United States, we are accustomed to our digital data being sold, traded, and generally existing outside of our control. Our data protections are fragmented at best, and we're not surprised when companies face no repercussions for handling our data recklessly, resulting in countless data breaches. (On the bright side, I've racked up about $54 this year from compensation related to data breaches, plus multiple simultaneous FREE subscriptions to identity theft monitoring.)

Yet for all this digital recklessness, proving our identity in the physical world has remained surprisingly private. When we flash our plastic driver's license to a bartender, hotel clerk, or security guard, something remarkable happens: no trace is left behind. This is thanks to an analog relic: the humble plastic driver's license. Since Americans use driver's licenses for many activities beyond driving, this accidental privacy protects a large swath of our lives, offering a rare sanctuary in a pervasively-surveilled world. 

A shift to mDL would affect Americans disproportionately. Our broad use of driver's licenses, plus lack of comprehensive data protection like GDPR, risks comprehensive surveillance–and ultimately, control–of our daily lives. We must be intentional about these tradeoffs; digitization doesn't have to equal surveillance.

The [\#NoPhoneHome](https://nophonehome.com/) movement has highlighted this principle, advocating broadly rather than targeting any specific technology. But mDL has received significant attention due to its "server retrieval" capabilities. In those discussions, I've felt we've been operating from different assumptions. It clicked for me when I realized many of the most vocal proponents don't live in the US—we use driver's licenses so differently. Understanding this difference is crucial. In this blog, I'll explain why mDL poses unique risks in America.

## **How Americans Actually Use Driver's Licenses**

In the mDL discussions, we've been operating from different assumptions because most of the world doesn't understand how Americans *actually* use driver's licenses. Unlike many countries that have widely-used national ID cards for identification and separate licenses for driving, the United States uses driver's licenses as the *de facto* national identification for countless daily activities:

* **Age verification:** Buying alcohol at dinner, picking up cold medicine  
* **Basic commerce:** Hotel check-ins, large purchases, picking up packages  
* **Healthcare:** Prescription pickup, doctor appointments, insurance verification  
* **Building access:** Office buildings, schools, apartment complexes  
* **Financial services:** Opening bank accounts, mortgage applications, investment accounts  
* **Employment:** Job applications, workplace access, background checks  
* **Government services:** Voting, federal buildings, social services

Mobile driver's licenses are being rolled out in some states, but most of us still exclusively use plastic cards. In many cases, the attendant simply looks at the card, and no record is kept. Believe me, I now watch like a hawk. Recently confirmed fully offline verifications include: picking up packages at the post office, checking into a hotel, picking up a prescription.

## **What We're Losing: From Anonymous to Tracked**

What stands out about current American driver's license usage is how often no record is kept at all. A bartender glances at your birthdate and hands the card back\[1\]. A security guard checks your name and waves you through. A hotel clerk looks at your ID and returns it without scanning. These everyday interactions—the bulk of our daily ID usage—leave no digital trail whatsoever.

mDL eliminates this category entirely. Every transaction, no matter how mundane, now creates digital records in both the mDL reader and your phone. Every “flash” of your license now creates two distinct receipts, each of which survive the other being deleted.

**Guaranteed for ALL Transactions:**

Transaction logs enable detailed records of:

* **Where** you went (GPS coordinates, venue identifiers)  
* **When** you went (precise timestamps)  
* **What** you accessed (which data elements were requested)  
* **How often** you visit locations (pattern analysis)

**The Corporate Surveillance Risk:** Without enforceable restrictions, wallet providers could sell "anonymized" transaction logs to data brokers. But location and time patterns make re-identification trivial, especially with the granular data mDL provides.

**The Government Surveillance Layer:** AAMVA recently announced a ban on server retrieval, but this represents "privacy by policy"\[2\]—an organizational rule that could be nuanced, exempted, or fully reversed at any time. **If this policy changes or states ignore it, the government gets notified of ALL transactions, making buying beer equivalent to opening a bank account in terms of government surveillance.** 

**Your phone becomes a surveillance database that:**

* Stores verbose transaction logs on your device  
* Stores rich metadata about your movements, habits, and associations  
* Is accessible to wallet providers for commercial purposes (e.g. building ad profiles or even serving ads)  
* Is searchable by authorities (potentially without warrants under current law)  
* Offers no easy way to delete or control this data

This dual threat—guaranteed corporate tracking plus potential government monitoring and control—becomes *uniquely* dangerous when applied to American ID usage patterns.

## **Why This Is Uniquely Dangerous in America**

Because Americans use driver's licenses for everything, and because we lack federal comprehensive privacy law like GDPR, the mDL standard in its current form enables comprehensive life tracking in a way that wouldn't happen in countries with:

1. More limited driver's license usage, or  
2. Better data protection frameworks

In the United States, this creates a perfect storm of surveillance risks.

### **Fragmented Protection**

While Europe has GDPR's comprehensive protections to help counter corporate surveillance, America has a patchwork of state laws with huge gaps—no federal privacy law, wildly different state protections, and limited enforcement compared to European regulators. In the US, this mDL spec becomes a leaky boat of privacy risks.

### **Universal Usage Amplifies All Risks**

Since Americans use driver's licenses for everything from mundane use-cases like buying beer to more privacy-critical ones like voting, both corporate and government surveillance become comprehensive life tracking systems. A European who uses a digital driver’s license occasionally faces limited exposure; an American using mDL faces total behavioral monitoring.

Consider this: count how many times you show your license in the coming month, then imagine each of those interactions being logged by the government, the business you're showing it to, and your own mobile wallet app—potentially making that data available to other vendors as well.

## **Mission Creep Guaranteed**

The surveillance infrastructure built for basic ID verification will inevitably expand beyond in-person transactions. Already proposed extensions include online age verification for websites and social media account verification through browser APIs\[3\] like the W3C Digital Credentials API. This would extend mDL surveillance from physical locations into web browsing, linking your government-issued identity to every online interaction that requires verification\[4\]. Each additional use case amplifies the surveillance risks exponentially..

## **The Window Is Closing**

Mobile driver's licenses are already rolling out across American states with varying levels of privacy protection. A spec dealing with digital identity needs to meet a higher bar and deserves more scrutiny—this makes the standard stronger.

The question isn't whether America will get digital identity systems—it's whether we'll demand American-style privacy protections that account for how Americans actually use identification in daily life, and whether we'll build privacy-by-design protections rather than relying on flimsy and easily-changeable policies.

This type of context-specific analysis would strengthen international standards. Identity solutions will never be one-size-fits-all. We do not need to accept a "take it or leave it" framing\! Americans need not adopt the mDL standard as-is because other nations do. As I've laid out here, everything about our use of driver's licenses is different.

The tragedy is that none of this surveillance is necessary for the legitimate benefits of digital IDs. We can have fraud reduction, convenience, and better security without comprehensive life tracking by multiple parties.

We have one chance to get this right. The choice is ours: adopt standards designed for different privacy contexts than ours, or demand privacy protections that account for how Americans actually use driver’s licenses in daily life and preserve the accidental anonymity we currently enjoy.

*Thanks to Juan Caballero, Sharon Leu, Steven McCown, Timothy Ruff for the helpful suggestions and revisions.* 

## Footnotes

\[1\] For those interested in the details, whether a trace of the identity verification is left behind varies based on whether documentation is required for compliance purposes, state ID scanning mandates, and whether transactions happen in-person or remotely. Some states require ID scanning for alcohol or restricted substance purchases, but such in-person transactions leave no record in most states. By contrast, higher-stakes transactions like opening bank accounts create audit trails. mDL transforms all categories into tracked events with mandatory digital logs.

\[2\] We’ll discuss privacy by policy and how this can be improved in the next blog.

\[3\] See for example [https://developer.chrome.com/blog/digital-credentials-api-origin-trial](https://developer.chrome.com/blog/digital-credentials-api-origin-trial) 

\[4\] I encourage you to read Brave’s concerns about the Digital Credential API, including that content and services would increasingly be gated behind digital ID requirements, transforming the open web into an "attributed web" where anonymity disappears.  

