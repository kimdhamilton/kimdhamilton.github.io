---
layout: post
title: Even the Experts Didn't Know
subtitle: How a Simple Presentation Revealed mDL's Latent Surveillance Problem
categories:
  - Driver's License
  - Privacy

---

*Part 1 of a series on Mobile Driver's License privacy considerations. I originally wrote this immediately after IIW, and updated it to reflect subsequent developments.*

Mobile Driver's Licenses (mDLs)—digital versions of your physical driver's license accessible through a smartphone app—are rolling out across states and countries right now. Based on the [ISO 18013-5 standard](https://www.iso.org/standard/69084.html), mDLs promise greater convenience for individuals and reduced fraud for businesses and government agencies. Surely we all understand what we're getting into, right? Well, a group of identity experts were surprised to discover what some are calling "latent surveillance by design" embedded in these systems. 

The revelation came at the Internet Identity Workshop, where digital identity experts gather to discuss the future of identity systems. Steve McCown's presentation about mDLs seemed routine at first. But his straightforward approach, showing excerpts from the official specification, revealed tracking capabilities that even the people designing and building these systems hadn't fully grasped.

What happened next sparked conversations across the digital identity community and beyond, leading to much-needed awareness and the beginning of progress. Much more work remains, as we'll explore throughout this series. This part focuses on Steve's session and the immediate response it triggered.

## **The Setting**

It was the 40th gathering of IIW — a biannual "unconference" where participants set the agenda each day. IIW attracts a largely technical audience of people who write standards, build identity systems, and advise governments on digital ID policy. Most sessions focus on specialized protocols and implementation details, so it probably goes without saying that many sessions are somewhat dry, but not this one.

[Steve McCown](https://www.linkedin.com/in/mccown/), a Digital Identity Architect and Utah Privacy Commission Advisor, had systematically reviewed the ISO mDL specification, discovering potential surveillance implications many hadn't fully appreciated.\[1\] As a white hat hacker with years of experience identifying vulnerabilities in computer systems and networks, Steve has an eye for potential security and privacy risks that others might miss.

Steve teamed up with [Chris Bramwell](https://www.linkedin.com/in/christopher-bramwell-26815515/) (Utah Privacy Officer) and [Timothy Ruff](https://www.linkedin.com/in/rufftim/) to hold an IIW session presenting his findings, combining perspectives from industry, government, and privacy advocacy.

Steve's presentation turned out to be exactly what was needed. Using excerpts from the ISO specification, he showed the audience what the standard actually enabled. No interpretation, no spin—just the technical details from the spec presented in black and white—that made the surveillance implications undeniable:

1. The ISO mDL standard includes latent "phone home" capabilities that enable targeted tracking  
2. If these capabilities are activated in your mDL, you won't necessarily know it  
3. Issuers can remotely enable or disable this tracking without your knowledge

For an audience of technical experts who thought they understood digital driver's licenses, these revelations were eye-opening, and somewhat embarrassing.

[See the slides here](https://nophonehome.com/mdl-privacy-concerns/).

## **How mDLs Work: The Two-Path System**

Before diving into the concerns, let's understand how mDLs work. The ISO mDL standard (18013) describes three roles:

1. **mDL Holder** ("holder"): A person with an mDL stored in an app on their mobile device  
2. **Issuing Authority** ("issuer"): The organization that creates the mDL. Typically a government, such as a state DMV, or their contractor   
3. **mDL Verifier** ("verifier"): Anyone who needs to check your ID. Examples include bartenders, TSA agents, pharmacy staff, etc.

The tool used by the verifier to read and verify your mDL is called an **mDL reader**. Refer to Figure 1 (excerpted from the standard):

<img src="../images/mdlInterfaces.png" width="600" alt="Figure 1: mDL Interfaces" title="Figure 1: mDL Interfaces" />

The standard includes two methods for retrieving your license data:

1. **Device Retrieval**: The mDL reader retrieves your mDL data directly from your phone via Bluetooth or NFC, requiring no internet connection. Like showing a physical ID, the data exchange stays between you and the verifier\[2\]. *(Interface 2 in Figure 1\)*  
2. **Server Retrieval**: The mDL reader contacts the issuing authority's servers to retrieve your mDL data, which is referred to as "phone home". *(Interface 3 in Figure 1\)*

## **Steve's Key Discoveries**

Steve's presentation highlighted several concerning implications of the specification that weren't widely understood:

**Breaking the Three-Party Model with "Phone Home"**: Many emerging digital identity architectures are built on a three-party model that’s foundational to decentralized identity—the issuer issues credentials to the holder, and the holder shares credentials directly with the verifier, but verification events do not "phone home” to the issuer. 

Many in the audience were familiar with server retrieval—where the mDL reader contacts government (or their contractors’) servers to fetch credential data instead of getting it from your device—but had been assured by others in the identity community that "no one implements it" or "it's going away" for many years. So they were surprised when Steve showed that server retrieval was prominently featured in the specification.

This "phone home" functionality breaks the three-party model by creating a direct line of communication between verifiers and issuers during every verification event. When active, server retrieval enables a record of when, where, and potentially why your ID was checked. These individual retrieval events can be centrally logged, recorded, and over time aggregated to build a detailed profile of your activities—creating a "funhouse mirror" representation of you that lacks context. The capability to systematically track and profile citizens' daily activities is, by definition, surveillance.

The idea that mDL verification could effectively resort to a centralized architecture, even for just some users, ran counter to this foundational assumption that had guided many digital identity experts’ work for years.

**Stealth Updates Without Transparency:** But it gets worse. Steve showed how an issuer can remotely switch between these modes for any user or groups of users without their knowledge or consent:

1. An issuer starts with device retrieval for all users  
2. Later, they can remotely add server retrieval "tokens" to some users' mDLs during regular updates (typically every 30 days)  
3. When those users' IDs are scanned, the mDL reader detects the token and retrieves credential data from issuer servers instead of the user's device  
4. The user has no way to know that server retrieval has occurred

This enables ***targeted*** tracking and data collection where some users' activities are tracked while others aren't—and users have no way to know which group they're in or that their data is being collected without their knowledge or consent.

**Latent Surveillance Capabilities:** Steve's reading of the specification suggested that mDL readers must implement both device and server retrieval modes. This interpretation wasn't challenged by session attendees, including contributors to the specification. As the audience discussed, this seemed to imply that the mDL reader had to be “complicit” in enabling surveillance by allowing phone home functionality even if it remains initially inactive.

*After Steve's presentation, I purchased my own copy of the specification to investigate whether server retrieval is required. What I found was more complicated but no less troubling: the ambiguity may lead implementers to understandably "go ahead and implement it." This doesn't resolve the privacy concerns; it makes them worse by creating uncertainty about what systems actually do.*

*This question proved sufficiently complex that it deserves its own deep dive, which we'll explore in Part 2 of this series.*

## **A Community Divided**

The IIW community reaction revealed something unexpected: they were reading from different playbooks. Steve presented his findings in two separate sessions at IIW, and the responses were starkly different.

### The Concerned Voices

The more alarmed response came from attendees in the first session. These were digital identity experts who understood that phoning home during verification goes beyond typical 'linkability' risks—rather than simply leaving traces that could be connected later, it directly transmits your identity and location to the issuer in real-time, enabling comprehensive centralized tracking by issuers, and unknown future consumers, across all interactions. Since avoiding this privacy problem has well-established technical solutions, they assumed community consensus against building it into new systems. Finding it embedded in the mDL specification demonstrates the difficulties of comprehensive privacy review when technical standards are not freely available to researchers, advocates, and the broader technical community.

[Jay Stanley](https://www.linkedin.com/in/jay-c-stanley/) of the ACLU, who has raised awareness about this and other concerns in the mDL spec for years, was in attendance and described what he called "inherently authoritarian capabilities."

Core contributors to the mDL specification were present, and they acknowledged that server retrieval functionality was included as a compromise because some countries require it. They explained that the technical capability exists in the specification, and preventing unwanted data collection requires individual implementers  to create appropriate policies or regulations.

This explanation only frustrated privacy advocates in the audience. [Joe Andrieu](https://www.linkedin.com/in/joe-andrieu-a0528/) responded, with support from other attendees, "they should rise to our level; we shouldn't lower to theirs"—referring to the concern that we might be naively building infrastructure with latent surveillance capabilities that authoritarian governments could exploit.

The discussion led to disturbing potential implications, including a pointed question: "Does this mean an implementer of mDL must effectively help foreign governments spy on their citizens, even if it was against local policy or regulations?" 

These attendees questioned whether technical standards should enable the lowest common denominator of privacy protection—or aspire to something better, like a default expectation of non-surveillance that authoritarian countries can build something atop if they wish to.

### The Pushback

The second session had a more guarded dynamic, but the pushback clarified the stakes. Some attendees seemed less surprised by Steve's findings, which he repeated—word had apparently spread from the first session, and they came prepared with counterarguments that took several forms:

**“Don’t you *have* to phone home for real-time status checks?”** This revealed a common misconception that credential verification requires contacting the issuer for the status of a specific credential. But avoiding this is a basic goal of decentralized identity systems—credentials can and should be verifiable without phoning home.

**"But if you're pulled over by police…"** That's a fair exception—police already access extensive data during traffic stops. The real concern is that mDLs are being designed for countless everyday uses such as pharmacy pickups and age verification at bars. Do we want those routine interactions to enable surveillance?

**"We just need better policies and regulations."** True, but this misses a crucial point: technical architecture shapes what's possible. Why build surveillance capabilities and hope policy will constrain their use?

**"At least people are building something."** This pragmatic view drew the sharpest response. Timothy Ruff countered: "You're making a value judgment—valuing expediency over privacy.” The logical next question is, are we comfortable with that trade-off?

## **Why This Is Different**

The discussion, although contentious at times, revealed why the digital identity community had been talking past each other. The debate exposed different comfort levels with embedding surveillance capabilities and trusting policy solutions to constrain their use. But this isn't just another privacy debate—it's fundamentally different in several ways:

**Not Everyone Knows the Risks:** some said the risks were well known and could be addressed through appropriate regulations. But this assumes governments implementing these systems understand the privacy implications and will create protective policies. Do they?

**The Rules Can Change:** Steve and others highlighted a more fundamental problem. Policies can be ignored, or changed. By embedding surveillance capabilities directly into the technical specification, we're creating permanent infrastructure for tracking—regardless of current protections.

**Beyond Typical Privacy Vulnerabilities:** This goes far beyond standard privacy concerns. The server retrieval capabilities in mobile driver's license standards define infrastructure that enables systematic, centralized data collection across daily activities. This isn't an unintended consequence—it's an architectural feature that can trivially enable persistent record-keeping of when and where you use your credentials, creating patterns that can be analyzed long after the original transaction by unknown third parties. Even worse, because verification can require real-time server contact, the issuing authority gains the ability to approve or deny credential use in the moment—effectively enabling digital identity deplatforming.

**The Invisibility Problem:** Perhaps most troubling, users have no way to detect when they're being monitored. Unlike a visible camera or an obvious data request, server retrieval operates silently. Users can't tell if their verification triggered surveillance, or when their monitoring status changes. This violates basic expectations of user agency and informed consent.

**Why the US Context Matters:** The concerns were amplified by the American context, where driver's licenses serve as de facto national ID cards used everywhere from TSA checkpoints to pharmacy pickups. Unlike countries with purpose-built national ID systems, Americans use driver's licenses for countless daily interactions, meaning the surveillance potential extends far beyond driving-related activities. Further, the U.S. lacks comprehensive data protection regulations that might mitigate this.

The fundamental question: Do we accept surveillance capabilities now and hope they won't be misused later? Or do we design systems that make surveillance technically difficult from the start?

## **What's Next**

Steve's presentation sparked questions and soul-searching within the digital identity community. The questions spanned technical and policy concerns: Is server retrieval actually required or truly optional? How do real-world implementations handle this choice? Can policy alone provide adequate privacy protection?

For my part, it launched a deeper investigation into server retrieval-related implementation requirements. This proved more frustratingly complex than expected, and we'll explore that in Part 2 of this series.

But this also triggered significant reflection: these surveillance capabilities had been hiding in plain sight. Many of us felt we had collectively dropped the ball on a blatant privacy issue, but recognizing that became the first step toward picking it back up. As Timothy Ruff put it, we’re the “last line of defense.” This started uncomfortable conversations leading to hints of real progress. In fact, just three weeks later, AAMVA announced they were updating their guidance to prohibit issuer use of server retrieval—a promising step, though other forms of linkability and tracking risks remain. We'll talk about this in part 3 of the series.

Today's architectural choices are being embedded into tomorrow's identity infrastructure. Technical standards and privacy policies can work together—if we're honest about what we're building and make surveillance-resistant choices from the start.

---

**Resources:**

* [IIW 40 mDL Privacy Concerns Presentation](https://nophonehome.com/mdl-privacy-concerns/)  
* [ISO/IEC 18013-5:2021 ISO-compliant driving licence, Part 5: Mobile driving licence (mDL) application](https://www.iso.org/standard/69084.html)  
* [ACLU Digital ID State Legislative Recommendations](https://www.aclu.org/report/digital-id-state-legislative-recommendations)

**Footnotes**:  
\[1\] Why did other identity experts miss this? Unless you are directly involved in the ISO technical committee developing this specification, you need to purchase it (around $300 USD). Because it is undergoing updates, it’s also a bit of a moving target. The costs add up, so many rely on summaries, excerpts shared by colleagues, or insights from technical committee participants. I purchased my own copy after Steve's presentation.

\[2\] Even this isn’t complete protection against tracking—the mDL reader could still log your information, and your mDL app might record transaction details. The ISO specification provides guidance but doesn't enforce privacy protections. We'll cover how that works in a subsequent post.
