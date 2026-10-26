# h1 CyberScience
## Science hunt
Emerging Challenges in Threat Modeling for GenAI-Augmented Systems: A View from the Trenches
Nicolás E. Díaz Ferreyra, Manish Mahesh Kumar, Nohemí Villarreal, Pankaj Pantel, Immo Brueggemann, Riccardo Scandariato

Comments:	Accepted at the 2026 International Symposium on Empirical Software Engineering and Measurement (ESEM)

Subjects:	Software Engineering (cs.SE); Cryptography and Security (cs.CR)

Cite as:	arXiv:2607.28431 [cs.SE]
 	(or arXiv:2607.28431v1 [cs.SE] for this version)
 
https://doi.org/10.48550/arXiv.2607.28431

## Review of the review
A brief summary around these questions:
- What are the key areas being researched?
  - RQ1: How effective are state-of-the-art threat modeling techniques in identifying GenAIspecific security issues in an SME setting?
  - RQ2: How do practitioners perceive the adoption and integration of these techniques in an SME context?
- What's widely agreed upon?

Although current techniques can capture prominent GenAI-related threats such as prompt injection and data poisoning, they provide only limited support for broader architectural, supply-chain, and human-centered risks. The future of GenAI-aware TM depends on combining comprehensive threat coverage with lightweight, tool-supported, and actionable integration into software development practice.
  - RP1: GenAI-aware TM approaches should explicitly incorporate knowledge of supplychain security into their frameworks while supporting some degree of automation.
  - RP2: Future work should explore prompt-guided and checklist-supported workflows for integrating GenAI-aware TM into LLM-assisted development practices.
  - RP3: GenAI-aware TM approaches should account for developers’ over-reliance on LLM-generated outputs by modeling human-centered threat propagation paths and identifying intervention points across the system architecture.
  - Findings RQ1. Although the evaluated Threat Modeling (TM) techniques identified several GenAIrelated issues, their coverage was strongest for input- and model-interaction threats (e.g., Prompt Injection, Data and Model Poisoning). Coverage was limited or absent for categories requiring broader architectural, supply-chain, or human-centered reasoning (e.g., Supply Chain Vulnerabilities and Excessive Agency). M3 provided the broadest support due to its tool-supported analysis and dedicated AI-oriented modeling syntax.
  - Findings RQ2. Practitioners rated M3 highest across all survey dimensions, particularly for its support in surfacing GenAI Threats and its relatively low perceived Effort. M1 and M3 received higher scores than M2 for Effectiveness, Awareness, Actionability, and Integration. Across methods, Socio-technical Threats received the lowest scores, consistent with the RQ1 findings. Participants also emphasized the need for better integration with existing development workflows, especially issue-tracking and security review processes.

_M1 – AI-as-a-Service (AIaaS) Framework. Relies on Data Flow Diagrams (DFD)-based system representations and structures the analysis around asset groups such as Data, Model, Environment, and Process. For each asset category, the framework provides STRIDE-based threat listings along with prospective mitigation actions._

_M2 – Attacks on Dataset, Model and Input (ADMIn) Framework. It adopts an attackcentric perspective around three major attack surfaces, namely Datasets, Models, and System inputs. The analysis is structured through DFD-like architectural representations and predefined attack categories associated with each attack surface. The method further provides guidance on threat prioritization and mitigation activities._

_M3 – ThreatFinderAI. This approach extends traditional DFDs with AI-specific assets (e.g., prompts and pre-trained models), which are subsequently analyzed through attack graphs and risk scenarios. Threat identification is semi-automated through the integration of external security knowledge bases such as MITRE ATLAS and OWASP AI Exchange. Unlike M1 and M2, this method is tool-supported._

- What are the open questions?
  - OE1: What were the top 3 most valuable threats identified across the methods, and why?
  - OE2: What would have to change for this method to be adoptable in your workflow?

## Threat modeling quickrun
Create two risks and decide what to do with them. Imagine the details. Be brief, but specific. (This task does not require technical tests on a computer)
Company

Crown jewels - data, business continuity, reputation, money.

Bad guys - What do they want? How are they going to get it? Why us? (COI - Capability, Opportunity, Intent)

List risks (only 2 example risks here). Likelyhood x impact = estimated value.
  - Yes, euros please. And percents. Ballpark, but numbers required.
  - Take biggest risk

What shall we do with that one biggest risk (META - mitigate, eliminate, transfer, accept)

## Voluntary bonus
Create an alert that emails you interesting articles. Good for your future thesis. Start with a wide net, then reduce it after a couple of days; and reduce it more after a week. You want to be happy to get email of a new article.

## Voluntary bonus
Install Linux on a virtual machine. Debian or Kali.

## Voluntary bonus
This task requires a computer and some practical command line knowledge. Solve the puzzle:

==gCh8mclRFIs8GbsVGS
