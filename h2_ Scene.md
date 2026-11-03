# h2 Scene

## A - Podcast Summary
### The intention of getting a company to send payments to the wrong person
[Ep 124: Synthetic Remittance - Darknet Diaries podcast](https://darknetdiaries.com/transcript/124/)

Evaldas Rimasauskas, 43yr old in 2012, was living in Vilnius - capital of Lithuania. Using social-engineer and BEC (Business E-mail Compromise), Evaldas and his small team managed earned the organizational and payment relationships around Facebook, Google with Quanta Computing.

He then imitated the trusted supplier - Quanta Computing and altered payment information.

Over the next 2 years, he extracted $23 million from Google and $98 million from Facebook. Someone from the victim companies started noticing the scam and traced back which e-mail it was that switched banks. They realized the domain wasn’t exactly the same when they got this e-mail, one that looked like Quanta’s.

The investigation found out who owned the lookalike domain (to figure that out, you can do a WHOIS lookup on a domain). Evaldas made his mistake.  He registered it under his own personal e-mail address.

### How could the security team help defend against this?

A lot of tools that are getting better at detecting this sort of thing, such as identifying when a lookalike domain has e-mailed you, or tools that just do basic domain reputation checking and then quarantine any e-mails that just don’t look right. Security is everyone’s responsibility in a company

## B - Blog post Summary
### Studying Fraudulent North Korean IT Workers
[Schneier on Security - Researchers set up a fake start-up company to study fraudulent North Korean IT workers](https://www.schneier.com/blog/archives/2026/10/studying-fraudulent-north-korean-it-workers.html)

Security researchers invented a cryptocurrency startup, advertised developer jobs, and hired 3 people they believe were North Korean operatives. Every virtual machine the company issued was recording.

The onboarding paperwork revealed all 3 new hired had had fake identity (SSN, driving license and bank account) with method such as forged or altered using AI image editing software and AI job-application and interview-assistance extensions.

A successful placement gives the operative a real employee account and access to source code and internal systems. North Korean IT workers then wired their salaries to parent North Korean agencies.

In April, The Justice Department sentenced 2 US facilitators over a separate scheme that placed workers at more than 100 US companies on at least 80 stolen identities and earned North Korea more than $5 million. The operation was a sequel. Another scheme is they became the employer, building a fake DeFi protocol called Ballena Azul. Then a recruiter trawling GitHub for facilitators delivered the first developer. That developer vouched for a friend, who vouched for a third. All 3 ran dxdiag, systeminfo, and wmic to profile their machines.

The report places infrastructure on Vultr and Gorilla Servers and says AstrillVPN exit nodes ran throughout.

### What can be done to limit this risk?

The researchers advise periodic identity checks rather than one at hire, in-person verification for remote-first companies, recruiter training, and blocking AstrillVPN.

## C - Science that

The [podcast](#a-podcast-summary) that I chose illustrates the [review paper](./h1_CyberScience.md)'s concern that architecture-focused methods can overlook an attack whose critical vulnerability is organizational trust. No model, database, or payment platform necessarily had to be technically compromised. The attacker manipulated the meaning attached to ordinary business artifacts such as invoices, domains, signatures, and bank-account details.

The review paper found that threat models struggle with human-centered and socio-technical risks. This reflected in the podcast that the attack worked because employees trusted a familiar supplier identity and fell for the changed payment details. As a result, a technically secure payment system can still fail when its business verification process is weak, which would be the larger lesson from this perspective.

A fresh security event in the context of the larger understanding could be the compromise of LiteLLM version 1.107.0 on October 2026 - a malicious package appeared to be a legitimate release because of a maintainer identity exposed months earlier but reportedly never revoked, and attackers used this to make successful build and signing process.

## D - Download Debian
Download Debian 13-Trixie installation image on the computer you'll use in the class. (Yes, this task is literally just downloading the ISO. Installing is a voluntary task for now.)
Go to Debian.org. On the Other downloads, under heading "Try Debian live before installing", choose "Live Xfce". The direct link for "Live Xfce" ISO image will soon become obsolete as new versions are published.
(Mac users: The linked image is for regular PC's, also known as amd64. If you have an M1, M2, M3, M4... Mac, it uses arm64 processor architecture, and you need to figure it out yourself. I suggest using UTM.)
## E - Voluntary bonus
Install Debian 13-Trixie Linux on a virtual machine. (Everyone will do this later on the class.)
## F - Voluntary bonus
Install a feed reader and follow some RSS / Atom feeds. (If time permits, everyone will do a version of this later.)
## G - Voluntary bonus
Read more blog posts and listen to podcasts. Link those news into larger theory framework, citing relevan articles.
