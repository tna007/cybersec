# h2 Scene

## A - Podcast Summary
### The intention of getting a company to send payments to the wrong person
[Ep 124: Synthetic Remittance - Darknet Diaries podcast](https://darknetdiaries.com/transcript/124/)

Evaldas Rimasauskas, 43yr old in 2012, was living in Vilnius - capital of Lithuania. Using social-engineer and BEC (Business E-mail Compromise), Evaldas and his small team managed to understand social and accounting infrastructure within large company such as Facebook and Facebook's business partner such as Quanta Computing.

They found out who's the one has the purchase power at Facebook and who's the one sending the invoice at Quanta Computing.

They set up fake invoice, fake domain, and fake business, all look-a-like the authentic ones from Quanta Computing, and told Facebook to update where payments should be sent when paying bills for Quanta.

The person at Facebook saw this e-mail and fell for it, making the change so that the payments are now sent to Evaldas’ bank instead of the real Quanta’s bank account.

Over the next 2 years, Evaldas extracted $23 million from Google and $98 million from Facebook. Someone from the victim companies started noticing the scam and traced back which e-mail it was that switched banks. They realized the domain wasn’t exactly the same when they got this e-mail, one that looked like Quanta’s.

The investigation found out who owned the lookalike domain (to figure that out, you can do a WHOIS lookup on a domain). Evaldas made his mistake.  He registered it under his own personal e-mail address.

### How could the security team help defend against this?

A lot of tools that are getting better at detecting this sort of thing, such as identifying when a lookalike domain has e-mailed you, or tools that just do basic domain reputation checking and then quarantine any e-mails that just don’t look right. Security is everyone’s responsibility in a company
## B - Blog post

## C - Science that
Link some theory, model or article you read in h1 CyberScience to a blog post or podcast episode you found here. Can you put a fresh security event in the context of larger understanding?

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
