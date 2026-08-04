# Pending Review

Proposed additions from study sessions. Nothing here is authoritative until promoted
to the appropriate reference file via `/promote`.

## Entry Format

```
### [TARGET-FILE] — [Short description]
Source: [web URL | tutor session | exam session]
Date: YYYY-MM-DD

[Proposed content to add]
```

---

<!-- Entries below this line -->

## BATCH: Inside Cloud and Security — CISSP Exam Cram (2026-08-03)

Extracted from two transcripts, both saved in `/notes/`:

- **2022 Full Course** — https://youtu.be/_nyZhYnCNLA — uploaded 2022-03-18, 7h56m, 72,624 words
- **2024 Addendum** — https://youtu.be/XZr2wLKdoVc — uploaded 2024-03-20, 2h38m, 22,489 words

The Addendum is keyed to numbered subtopics of the April 15, 2024 exam outline, so it is the
higher-authority source of the two. Author's errata: https://github.com/pzerger/cisspexamcram

Timestamps below cite the source video so any entry can be re-checked before promotion.

---

# SECTION A — CONFLICTS (resolve before promoting anything else)

Places where the source disagrees with a reference file or with a primary source.
**No file changes are proposed here.** Four of five resolve in favor of the existing
reference files. Read this section first.

### [CONFLICT — resolved, no change] Passing score is NOT 70%
Source: 2022 course @ 00:05:15; author's FAQ https://github.com/pzerger/cisspexamcram/blob/main/FAQs.md
Date: 2026-08-03

Course says "you need a seventy percent to pass." FAQ repeats it: "The score required to pass
the exam is 70%." ISC2 exam outline states **"700 out of 1000 points"** — a *scaled* score
derived from item difficulty, not a percentage of items answered correctly.

**VERDICT: reference files are correct. Source is wrong.** No change. See proposed TRAP 16,
which turns this widespread misconception into a trap entry.

### [CONFLICT — resolved, no change] Exam length and item count
Source: author's FAQ (stale); 2024 Addendum @ 00:00:00–00:02:00 (current)
Date: 2026-08-03

The FAQ still describes the June 1, 2022 change — 50 pretest items, 125-175 items, four hours.
That was accurate 2022-2024 but was reverted by the April 15, 2024 outline. The Addendum states
the correction directly: "it was a 4-hour adaptive exam with 125 to 175 questions moving down to
a 3-hour exam with 100 to 150 questions as of April 15th 2024 ... now we have only 25 unscored
questions where before there were 50."

Verified against https://www.isc2.org/certifications/cissp/cissp-cat ("100-150", "25 pretest",
"three hours") and the exam outline ("3 hours", "100 - 150", "700 out of 1000 points").

**VERDICT: reference files are correct.** All eight domain weights also match ISC2 exactly.
No change.

### [CONFLICT — source error, verified] FIPS 140-2 has FOUR security levels, not three
Source: 2024 Addendum @ 00:42:50
Date: 2026-08-03

Addendum states FIPS 140-2 has "three levels" and that FIPS 140-3 "has four instead of three."
NIST states FIPS 140-2 provides **"four increasing, qualitative levels"** (Security Levels 1-4).
FIPS 140-3 also defines four. The count did not change between the standards — the *requirements
at each level* changed.

**This error is NOT in the author's published errata.** Verified at
https://csrc.nist.gov/pubs/fips/140-2/upd2/final

Do not adopt the Addendum's level descriptions without checking them against FIPS 140-3 directly.

### [CONFLICT — needs your call] Waterfall backtracking
Source: 2024 Addendum @ 02:18:57 vs. reference/cissp-glossary.md D8 "SDLC Models"
Date: 2026-08-03

Glossary says Waterfall is "rigid, no backtracking." Addendum says the model "allows us to go
back and make corrections, but we can only return to a previous stage only one stage back."

Both are defensible: pure Waterfall (Royce) has no backtracking; the *modified* Waterfall taught
in the Sybex OSG allows returning exactly one phase. The CISSP generally tests the modified form.

**Suggested resolution** — amend the glossary line to:
`Waterfall (sequential phases; the modified form used on the exam permits returning one phase
back, no further)`. Your call; flagging rather than assuming.

### [CONFLICT — author errata, content error in video] IDS listed as a corrective control
Source: 2022 course @ 05:09:13; author's errata
Date: 2026-08-03

The video shows "intrusion detection system" in a list of **corrective** controls. Author's
errata confirms this should be **intrusion prevention system**. An IDS is a **detective**
control. Also at 00:18:56 the video shows "EPCA"; correct acronym is **ECPA** (Electronic
Communications Privacy Act of 1986).

No reference file change needed — the glossary does not repeat either error. Noted so you do not
absorb them from the video. Control-type classification is a recurring exam theme.

---

# SECTION B — PROPOSED ADDITIONS TO cissp-glossary.md

All entries below are absent from the current glossary (checked against all existing terms).
Style matches the existing file: `Term: definition.`

### [cissp-glossary.md] Domain 1 — 2024 outline additions
Source: 2024 Addendum @ 00:12:50–00:39:00 (subtopics 1.2.1, 1.3.4, 1.7.2, 1.9.9, 1.11.2, 1.4.5)
Date: 2026-08-03

Five Pillars of Information Security: Confidentiality, Integrity, Availability, Authenticity,
and Non-repudiation. None of the five concepts are new, but the "five pillars" phrasing appears
in the 2024 exam outline (1.2.1) and did not appear in the 2021 version. Recognize the phrase.

Security Control Framework: Provides a prescriptive set of safeguards and best practices to
protect assets — addresses the HOW of risk mitigation. Examples: NIST SP 800-53, ISO 27002.

Risk Framework: Provides a structured approach to identifying, assessing, prioritizing, and
managing risk to guide decision-making — addresses the WHY. Examples: NIST RMF, ISO 27005.

SABSA (Sherwood Applied Business Security Architecture): Security architecture framework and
methodology focused on aligning security with business goals. Provides a structured method for
designing, implementing, and managing security architectures. Cited in the 2024 outline under
BOTH security control frameworks (1.3.4) and risk frameworks (1.9.9) — it adds an architecture
layer usable alongside either.

Privacy vs. Confidentiality: Privacy is the RIGHT OF AN INDIVIDUAL to control how their personal
information is collected, used, and disclosed. Confidentiality is the DUTY OF AN ORGANIZATION to
keep private information secret. Privacy attaches to the person; confidentiality attaches to the
data. Under US law, confidentiality is a due care obligation.

PIA (Privacy Impact Assessment): Assessment that identifies what privacy data a system collects,
processes, or stores, and evaluates the effects of a breach of that data. Explicitly required by
several privacy laws including GDPR and HIPAA. Conducting one requires defining assessment scope,
data collection methods, and a data retention plan. Typically begins when a system or process is
being designed, but evolving regulation often forces assessment of existing systems.

Data Residency: The physical or geographic location where data is stored. Many countries impose
specific legal requirements on residency. Particularly difficult to establish in public cloud,
where data may be replicated across regions automatically.

External Dependencies: Entities outside the organization that it depends on for business
continuity, disaster recovery, or operations — ISPs, utility companies, recovery site providers,
generator fuel suppliers. Effectively part of the supply chain. Key principle: do not rely on a
single vendor for a critical function if that vendor could be impacted by the same event as you.
New topic at 1.7.2 in the 2024 outline.

Hardware Root of Trust: A defense against executing unauthorized firmware. Provides an immutable
anchor used to verify firmware and system integrity before boot. TPM and Silicon Root of Trust
are both implementations.

TPM (Trusted Platform Module): A hardware root of trust implementation — a dedicated chip that
stores cryptographic keys and verifies system integrity. Used by BitLocker full disk encryption
on Windows.

Silicon Root of Trust: A specialized chip or module embedded directly into device hardware
(servers, IoT) containing a unique, unchangeable cryptographic identity established during
manufacture — its "immutable fingerprint." If firmware is compromised, signatures no longer
match and the system is prevented from booting. Newly cited in the 2024 outline (1.11.2).

PUF (Physically Unclonable Function): Hardware component that generates a digital fingerprint
from the unique physical characteristics of an integrated circuit. When challenged, it responds
with an output derived from the chip's inherent manufacturing variations — impossible to clone
onto another device. Used for secure key generation, device authentication, anti-tampering, and
secure boot. Newly cited in the 2024 outline (1.11.2).

Encryption Export Controls: US companies may not export certain encryption technologies to
nations designated as restricted. Administered by the Department of Commerce. Privacy in the
United States is grounded in the Fourth Amendment.

Legal Hierarchy for Exam Answers: Laws are created by legislatures; regulations are created by
government agencies; standards dictate a reasonable level of performance (internal or from
industry bodies); frameworks are guidelines for improving security posture. Laws and regulations
carry civil or criminal penalties and therefore OUTRANK standards and frameworks when answer
choices conflict. See proposed TRAP 17.

### [cissp-glossary.md] Domain 3 — 2024 outline additions
Source: 2024 Addendum @ 00:40:19–00:59:00 (subtopics 3.1.11, 3.6.1, 3.6.3, 3.10)
Date: 2026-08-03

SASE (Secure Access Service Edge): Design philosophy closely related to Zero Trust network
architecture that converges networking and security functions and delivers them as an integrated
cloud service. Components: firewall services, secure web gateway, anti-malware, intrusion
prevention, CASB, and DLP. First described by Gartner in 2019. Pronounced "sassy." New at 3.1.11.

CASB (Cloud Access Security Broker): Policy enforcement point between cloud service users and
cloud providers that applies enterprise security policy to cloud resource access. A component
of SASE.

QKD (Quantum Key Distribution): Secure key exchange method using quantum mechanics that allows
two parties to generate a shared random secret key. Its essential property is eavesdropping
detection — interception introduces detectable anomalies, and protocols define an error-rate
threshold beyond which eavesdropping is assumed. QKD produces and distributes a key ONLY; it
does not transmit message data. Requires an authenticated classical channel, which limits its
practical advantage. Currently niche. NOT the same as post-quantum cryptography.

Level of Protection (key management): Encryption keys must be secured at the same level of
control or higher as the data they protect. The sensitivity of the data dictates the required
level, as defined in the organization's data security policy.

Key Recovery: Recovering a key for a user without that user's cooperation — for example after
termination or key loss. Distinct from key escrow, which is the mechanism that often enables it.

Key Destruction vs. Key Deletion: Key destruction removes an encryption key from its operational
location. Key deletion goes further and removes any information that could be used to reconstruct
the key.

Information System Life Cycle: Structured framework for managing an information system from
conception to retirement. New major topic at 3.10 in the 2024 outline, with nine phases:
(1) Stakeholder needs and requirements — establish baseline security expectations, CIA needs,
compliance requirements. (2) Requirements analysis — translate expectations into detailed,
actionable security requirements; map requirements to controls. (3) Architectural design —
security by design; threat modeling; least privilege; defense in depth. (4) Development and
implementation — secure coding, configuration hardening. (5) Integration — maintain integrity
during integration; find gaps arising from component interaction. (6) Verification and validation
— verification confirms the system meets requirements, validation confirms it meets stakeholder
needs. (7) Transition and deployment — protect data during migration, apply production
configurations. (8) Operations, maintenance, and sustainment — patching, monitoring, incident
response, change control. (9) Retirement and disposal — secure sanitization, hardware disposal,
compliance with retention requirements; primary goal is preventing data exposure.

### [cissp-glossary.md] Domain 4 — 2024 outline additions
Source: 2024 Addendum @ 00:59:00–01:17:24 (subtopics 4.1.2, 4.1.5–4.1.12, 4.1.17, 4.1.18)
Date: 2026-08-03

IPv6: 128-bit addressing, successor to IPv4's 32-bit scheme (~4 billion addresses).

Network Communication Methods: Unicast = one-to-one. Multicast = one-to-many (specific
recipients); supported by IPv4 and IPv6. Broadcast = one-to-all on a segment; **NOT supported by
IPv6** (multicast workarounds exist). Anycast = one-to-nearest/optimal recipient from a group;
supported natively by IPv6.

Converged Protocols (2024 additions): InfiniBand over Ethernet — allows remote direct memory
access over Ethernet, lower latency and higher throughput than Ethernet alone. CXL (Compute
Express Link) — open standard for high-speed CPU-to-device and CPU-to-memory connections. Both
newly cited at 4.1.5; the existing FCoE / iSCSI / VoIP examples still apply.

Transport Architecture Planes: Management plane handles configuration, monitoring, updates, and
security management (SNMP, NETCONF). Control plane manages routing and determines optimal paths
(OSPF, BGP). Data plane forwards packets based on control plane guidance.

Switching Types: Cut-through — forwarding decision made as soon as the first part of the frame
arrives; use when ultra-low latency or low cost matters. Store-and-forward — the switch waits for
the entire frame before deciding; use when reliability is essential or the network is unreliable.

Network Performance Metrics: Bandwidth = theoretical maximum capacity of a channel. Throughput =
actual transfer rate achieved, accounting for latency, packet loss, and congestion. Latency =
delay between send and arrival; inversely related to throughput. Jitter = variation in latency
over time; degrades real-time applications. SNR (Signal-to-Noise Ratio) = signal quality relative
to background noise; higher is better. Cited at 4.1.7.

Physical Segmentation: Out-of-band — physically separating network infrastructure into distinct
zones using separate hardware, providing alternate communication paths. Air gap — complete
physical isolation with no wired or wireless connectivity; used in classified government networks
and critical infrastructure (utilities, industrial control systems).

Logical Segmentation: Segmenting without additional physical hardware. In-band — separating
segments by configuring routers, switches, and firewalls (subnets, VLANs). VRF (Virtual Routing
and Forwarding) — multiple routing instances coexisting on one router simultaneously. Virtual
domain — a segment created through logical techniques; called a VRF domain in the VRF context.

Microsegmentation: Extends logical segmentation to a finer granularity by dividing applications
or workloads into small segments containing a specific workload or functionally similar nodes,
with policies targeted per segment. Limits the scope of an outage or breach and constrains
lateral movement — commonly described as limiting the "blast radius." Cited at 4.1.11.

Edge Network: Distributed network bringing compute and storage physically closer to end users.
Ingress/egress — entry and exit points for traffic, the boundary where monitoring and traffic
shaping are applied. Peering — direct interconnection between edge locations allowing traffic
exchange without traversing a central hub; reduces latency, cost, and hub bottlenecks. Caching —
storing popular content closer to users (CDN). Edge computing — containerized compute running
near users and devices, common in IoT; reduces data sent to a central cloud. Cited at 4.1.12.

VPC (Virtual Private Cloud): Virtual network of cloud resources in which one tenant's VMs are
isolated from another's. Separate VPCs can be isolated using public or private subnets and
segmentation. Called VPC in AWS and Google Cloud, VNet in Azure. Cited at 4.1.17.

Network Monitoring and Management: Network observability — collecting data and visibility into
component status and traffic flows to support troubleshooting. Traffic shaping — managing volume
and priority of traffic types via QoS, rate limiting, and throttling. Capacity management —
tracking utilization and planning expansion to meet future demand. Fault detection and handling —
discovering, diagnosing, and responding to failed devices, connectivity loss, and slowdowns;
usually includes alerting and possibly automated failover. Cited at 4.1.18.

Intranet / Extranet / DMZ: Intranet — private network hosting internal information services.
Extranet — section of the network sectioned off to serve information to external parties.
DMZ (demilitarized zone, also called perimeter network) — an extranet for public consumption.

### [cissp-glossary.md] Domain 5 — 2024 outline additions
Source: 2024 Addendum @ 01:17:24–01:45:32 (subtopics 5.1.6, 5.2.1, 5.2.2, 5.2.6, 5.4.7, 5.5.5, 5.6)
Date: 2026-08-03

Roles vs. Groups: A group is a collection of users or devices sharing common access requirements
— it streamlines permission management at scale. A role defines specific rights and permissions
granted to groups, typically reflecting a job function or responsibility. In cloud platforms,
roles map to technical task sets and are often paired with time-limited (just-in-time)
activation. Cited at 5.2.1.

Passwordless Authentication: Authentication with no password factor. Implementations include
FIDO2 security keys, platform authenticators (e.g., Windows Hello for Business), and
authenticator apps using biometric unlock. Advantages: convenience, and materially reduced
phishing exposure — a user with no password has no password to be tricked into resetting or
disclosing. Disadvantages: hardware cost for security keys, biometric privacy concerns, and
device dependence. Currently considered the strongest practical authentication method.
Newly elevated to direct mention at 5.2.2.

FIDO2: Passwordless authentication standard using asymmetric cryptography. The user presents a
physical device (USB or NFC); the service issues a cryptographic challenge; the device signs it
with the private key; the service verifies the signature and grants access. The private key never
leaves the device.

OATH Token (Open Authentication): Open standard specifying time-based one-time password codes —
the familiar rotating six-digit code. Software OATH runs in an authenticator app using a seed
value. Hardware OATH is a key-fob device displaying a code refreshing every 30 or 60 seconds with
a pre-programmed seed. Do not confuse with OAuth (authorization framework).

Authentication Method Strength (weakest to strongest): password → SMS or voice callback (better
than password alone but no longer recommended) → authenticator app / software or hardware OATH
token → passwordless (FIDO2, platform authenticator). Useful for "which is MOST secure" items.

Zero Trust Principles: Three principles — assume breach, verify explicitly, and least privilege
access. Zero Trust treats identity as the control plane and has largely superseded the
"trust but verify" perimeter model. It is supported by, not a replacement for, defense in depth.

PEP (Policy Enforcement Point): Enables, monitors, and terminates connections between a subject
and an enterprise resource. Acts as the gateway that ENFORCES access control policy — for
example, requiring MFA for a request from an unexpected location. Resides in the DATA plane.

PDP (Policy Decision Point): Where access DECISIONS are made, based on user identity, device
health, and risk. Evaluates the context of a request — the who, what, where, when, and why — and
decides allow, deny, or apply additional controls. Resides in the CONTROL plane. Comprised of the
Policy Engine (decides) and the Policy Administrator (communicates the decision — a function, not
a person). Defined in NIST SP 800-207. Cited at 5.4.7.

Zero Trust Control Plane vs. Data Plane: Control plane contains adaptive identity, threat scope
reduction, policy-driven access control, the policy administrator, and the policy engine. Data
plane contains implicit trust zones, the subject and system, and the policy enforcement point.

Adaptive Identity: Varying the authentication challenge based on request context — user location,
device health, application used, and current risk level (often derived from user and entity
behavior analytics).

Service Account: An account used to run an application or service that requires privileged access
without human intervention. Also called a service principal. Cloud equivalents provide an identity
to a resource: managed identity (Azure), service role (AWS), service account (Google Cloud). Least
privilege and lifecycle management apply — provision when the application is deployed, deprovision
when it is retired. In cloud, a resource-tied identity is cleaned up automatically when the
resource is deleted; on premises it typically is not. Cited at 5.5.5.

Password Vault vs. Cloud Secrets Management: A password vault stores credentials locally under
strong encryption so users need not memorize them — only as secure as the master password
protecting it. The cloud equivalent for application secrets is a managed key/secret store (Azure
Key Vault, AWS KMS, Google Cloud KMS) offering programmatic API access for DevOps and CI/CD, with
access control at the vault and individual secret level. A "secret" is anything access-controlled:
API keys, passwords, tokens, or cryptographic keys. Cited at 5.2.6.

### [cissp-glossary.md] Domain 6 — 2024 outline additions
Source: 2024 Addendum @ 01:45:32–02:04:46 (subtopics 6.1.4, 6.2.2, 6.5.4)
Date: 2026-08-03

Security Testing Teams: Red team — emulates the tools and techniques of likely attackers as
realistically as possible; offense. Blue team — the internal security team defending against both
real attackers and red teams; defense. Purple team — exists to maximize the effectiveness of the
red and blue teams; effectively process improvement, not a third combatant. White team — oversees
the engagement and acts as judge or referee; NOT named in the exam outline but commonly tested.
Cited at 6.2.2.

Audit Location (on-premises / cloud / hybrid): On-premises — auditors typically need physical
access to hardware and data centers; the organization retains greater control and auditors have
direct visibility. Cloud — security is a shared responsibility; audit focus shifts to how the
organization CONFIGURES the service; auditors rely heavily on provider documentation, service
configurations, and APIs for evidence; customer right to audit is usually limited. Hybrid —
generally the most complex, because data flows and control effectiveness must be evaluated across
both environments, often with separate control sets. Appears at BOTH 6.1.4 (design and validate)
and 6.5.4 (conduct and facilitate) — the two are not duplicates; the context differs.

Right to Audit: A contractual right allowing a customer to audit a service provider for compliance
with agreed security requirements. In public cloud, contracts commonly substitute the provider's
own third-party audit reports (SOC 2, ISO 27001) for a customer-performed audit, because
accommodating every customer's audit is not feasible. Use of vulnerability scanners and
penetration testers against a CSP is constrained by the provider's terms of service and rules of
engagement.

Audit Sampling: Selecting a representative subset of a system's physical infrastructure to
inspect rather than auditing all of it. Necessary in cloud audits because geographic redundancy
and automatic replication can multiply the systems in scope several times over.

ISAE 3402 (International Standard on Assurance Engagements): Issued by the International Auditing
and Assurance Standards Board. Roughly the international equivalent of a SOC 2 report.

CSA STAR (Security, Trust, Assurance and Risk): Cloud Security Alliance certification program
demonstrating a cloud provider's compliance to a desired level of assurance. Two levels:
Level 1 is a complimentary self-assessment; Level 2 requires an independent third-party audit
against the CSA standard and is therefore stronger.

Bridge Letter: A document issued by a service organization covering the gap between the end of a
SOC report's audit period and the current date, attesting that no material control changes have
occurred. Provided when an audit has not been repeated on the expected interval.

SOC 2 Type II observation period: Assesses control effectiveness over time, typically by observing
operations for **at least six months**. (Extends the existing SOC 2 glossary entry, which states
"over a period of time" without the duration.)

### [cissp-glossary.md] Domain 7 — 2024 outline additions
Source: 2024 Addendum @ 02:04:46–02:15:26 (subtopics 7.2.3, 7.12.6)
Date: 2026-08-03

SIEM (Security Information and Event Management): System that collects log data from many sources
across the network and provides real-time monitoring, traffic analysis, and notification of
potential attacks. Key features: log centralization and aggregation, data integrity, normalization
into a common event schema, continuous monitoring, alerting, and investigative query support. Logs
have no value until reviewed — manually or through automation. NOTE: absent from the current
glossary and never mentioned in the 8-hour 2022 course; a genuine gap in both.

SOAR (Security Orchestration, Automation, and Response): Provides centralized alert and response
automation using threat-specific playbooks and runbooks. Response may be fully automated or
semi-automated ("single click"). Reduces mean time to detection and accelerates response by
operating at machine rather than human scale. In the 2024 outline SOAR **moved from Domain 8 into
Domain 7 (7.2.3)**, placed directly after SIEM (7.2.2) because the two are typically delivered
together.

Playbook vs. Runbook: A playbook is a document or checklist defining how to verify and respond to
an incident — the paperwork. A runbook implements playbook logic in an automated tool — the
technology. Some vendors use the terms interchangeably; for the exam, playbook = process,
runbook = automation.

DR Test Communications: Disaster recovery test communications must be tailored per stakeholder.
Internal — the DR team needs reliable real-time channels for coordination; management needs
periodic progress updates; the wider company needs advance notice and an all-clear. External —
customers need proactive notice of potential disruption and ETAs when impact occurs; partners need
timelines and agreed coordination channels where joint systems are affected; regulators in certain
industries may mandate advance notification or post-test reports for regulated systems. New topic
at 7.12.6.

### [cissp-glossary.md] Domain 8 — 2024 outline additions
Source: 2024 Addendum @ 02:15:26–02:31:00 (subtopics 8.1.1, 8.2.9, 8.4.5)
Date: 2026-08-03

SAFe (Scaled Agile Framework): Set of organizational and workflow patterns for implementing Agile
at enterprise scale. Built on three bodies of knowledge: Agile software development, lean product
development, and systems thinking. SAFe does not replace Agile — it adds layers needed to make
Agile work across many teams: cross-team coordination, strategic alignment to business objectives,
quality as non-negotiable, architectural guidance, cadence and synchronization through PI (Program
Increment) planning, and lean-agile leadership. PI planning is typically a quarterly exercise.
Brand new at 8.1.1 in the 2024 outline.

Scrum: An Agile methodology providing a specific set of rules, practices, and roles that put Agile
principles into action. Primarily used by software development teams.

Agile Values: Individuals and interactions over processes and tools; working software over
comprehensive documentation; customer collaboration over contract negotiation; responding to
change over following a plan. From the 2001 Agile Manifesto.

SAST (Static Application Security Testing): Analysis of software performed WITHOUT executing it.
Requires source code access; the tester has visibility into framework, design, and implementation.
Tests "from the inside out."

DAST (Dynamic Application Security Testing): Testing that communicates with and executes a running
application, typically a web application. Requires no source code and assumes no knowledge of the
underlying frameworks — a form of black-box testing. Tests "from the outside in."

IAST (Interactive Application Security Testing): Analyzes code for vulnerabilities WHILE the
application is being used, examining internal functions of the running application and reporting
in real time. Often built into CI/CD automated release testing. New in the 2024 outline (8.2.9).

Cloud Service Models: IaaS (Infrastructure as a Service), PaaS (Platform as a Service), SaaS
(Software as a Service). All three cited at 8.4.5 in the context of assessing the security impact
of acquired software.

Shared Responsibility Model: Security duties are divided between cloud provider and customer, and
the division shifts by service model (IaaS/PaaS/SaaS). The customer must know precisely which side
owns each control to avoid gaps and overlaps. Critical corollary: **accountability cannot be
transferred.** If the provider is breached and customer data is exposed, the organization's
responsibility to its own customers is unchanged. Compliance is also assessed per service — a
provider's PaaS database may be PCI compliant while another of its services is not.

---

# SECTION C — PROPOSED ADDITIONS TO exam-traps.md

Existing file ends at TRAP 15. Numbering continues from 16.

### [exam-traps.md] Eight new traps
Source: 2024 Addendum and 2022 course, timestamps per trap
Date: 2026-08-03

TRAP 16 — The Passing Score Is Scaled, Not a Percentage
700 out of 1000 is a SCALED score derived from the difficulty of the items you answered.
It is NOT "70% of questions correct." You cannot compute your standing by counting right
answers, and a practice test where you scored 70% tells you nothing directly about passing.
This misconception is widespread — the popular Exam Cram course and its FAQ both state it
incorrectly. (Source conflict, 2022 course @ 00:05:15.)

TRAP 17 — Law and Regulation Outrank Standards and Frameworks
When answer choices put a legal or regulatory obligation against a standard, framework, or
best practice, the law wins. Laws come from legislatures, regulations from government
agencies, and both carry civil or criminal penalties. Standards and frameworks do not.
Order of priority for scenario questions: human safety → legal/regulatory → risk management →
business continuity → standards and frameworks. (2024 Addendum @ 00:34:16, 02:31:00.)

TRAP 18 — Playbook vs. Runbook
Playbook = the PAPERWORK. A document or checklist defining how to verify and respond to an
incident. Runbook = the TECHNOLOGY. The automated implementation of that playbook in a tool.
Some vendors reverse these in their product naming; the exam does not. (2024 Addendum @ 02:08:52.)

TRAP 19 — Red, Blue, Purple, and White Teams
Red = offense, emulating real attackers. Blue = defense, the internal security team.
Purple = maximizes the effectiveness of BOTH red and blue; it is process improvement, not a
third combatant fighting anyone. White = oversight, the judge or referee of the engagement.
Students most often mistake purple for "a mixed attack team." Red, blue, and purple are named
in the 2024 exam outline; white is not, but is commonly tested. (2024 Addendum @ 01:53:33.)

TRAP 20 — NIST RMF vs. NIST CSF
RMF (SP 800-37) targets FEDERAL GOVERNMENT AGENCIES and is MANDATORY for those it applies to.
CSF targets PRIVATE COMMERCIAL BUSINESS and is entirely VOLUNTARY guidance. Both address
cybersecurity risk management, so questions distinguish them by audience and obligation rather
than content. (2024 Addendum @ 00:18:10.)

TRAP 21 — Privacy vs. Confidentiality
Privacy is the RIGHT OF THE INDIVIDUAL to control their personal information.
Confidentiality is the DUTY OF THE ORGANIZATION to keep that information secret.
Privacy attaches to the person; confidentiality attaches to the data. Students treat them as
synonyms — the exam does not. (2024 Addendum @ 00:22:13.)

TRAP 22 — Policy Decision Point vs. Policy Enforcement Point
PDP DECIDES, and lives in the CONTROL plane. It evaluates identity, device health, and risk —
the who, what, where, when, and why. It is made up of the policy engine (decides) and the policy
administrator (communicates the decision — a function, not a person).
PEP ENFORCES, and lives in the DATA plane. It is the gateway that permits, monitors, and
terminates the connection. Defined in NIST SP 800-207. (2024 Addendum @ 01:34:33.)

TRAP 23 — SAST vs. DAST vs. IAST
SAST — static, no execution, REQUIRES SOURCE CODE, tests inside-out.
DAST — dynamic, executes the running app, NO source code, black-box, tests outside-in.
IAST — interactive, analyzes internal functions WHILE the app runs, real-time, usually wired
into CI/CD. IAST is new to the 2024 outline and is the one students have not seen before.
(2024 Addendum @ 02:20:57.)

### [exam-traps.md] Complex question types and the R.E.A.D. method
Source: 2024 Addendum @ 02:33:00
Date: 2026-08-03

Proposed as an extension to TRAP 13 (CAT Exam Behavior) or as a standalone trap.

Not every item is four-option multiple choice. Expect **hotspot** items (click the correct part
of a diagram) and **drag-and-drop** items (drag correct answers into a box). Both can be
converted into a standard multiple-choice problem and solved the same way — for drag-and-drop,
treat it as "select all that apply" across the candidate list; for hotspot, write out the viable
answer combinations and choose among them.

The author's R.E.A.D. method, worth recording as a procedure for any item type:
**R**eview — what is actually being asked; what is the true end goal; are laws or regulations in play?
**E**liminate — strike distracting detail and answers that are definitely wrong (removing two of
four moves a guess from 25% to 50%).
**A**nalyze — prioritize solution requirements against CISO priorities: human safety, risk
management, keeping the business running, legal/regulatory over standards and frameworks.
**D**ecide — evaluate remaining answers individually and look for the all-encompassing one that
subsumes the others; that is usually the best answer.

At 100-150 items in three hours you have roughly 1.2-1.8 minutes per item, so this has to become
automatic rather than deliberate.

---

# SECTION D — PROPOSED ADDITIONS TO frameworks-map.md

### [frameworks-map.md] NIST, ISO, cloud, and privacy law additions
Source: 2024 Addendum, timestamps noted inline
Date: 2026-08-03

Under "NIST Publications":
NIST SP 800-207: Zero Trust Architecture (policy decision point, policy enforcement point,
policy engine, policy administrator) — D5 (IAM), D3 (Architecture). @ 01:36:34

Under "ISO/IEC Standards":
ISO/IEC 27001:2022: ISMS requirements — the 2022 revision adds cloud security coverage and is
the certification the major CSPs hold. Addresses the WHAT and WHY. @ 00:20:12
ISO/IEC 27002:2022: Control implementation guidance supporting 27001 — access control,
cryptography, HR security, operational security, incident response. Substantially larger than
27001; addresses the HOW. @ 00:22:13
ISAE 3402: International assurance standard, roughly equivalent to SOC 2 — D6. @ 02:00:48

Under "Industry Frameworks":
SABSA (Sherwood Applied Business Security Architecture): Business-driven security architecture
framework — D1. Cited in the 2024 outline under both security control frameworks (1.3.4) and
risk frameworks (1.9.9). @ 00:16:07
CSA STAR: Cloud Security Alliance Security, Trust, Assurance and Risk certification; Level 1
self-assessment, Level 2 third-party audit — D6. @ 02:00:48
SSAE 18: AICPA standard governing SOC 1/2/3 reports — D6. (Already referenced inside the SOC 1
glossary entry but absent from this file.)

Under "Regulations and Standards":
FedRAMP (Federal Risk and Authorization Management Program): US government-wide standardized
approach to security assessment, authorization, and continuous monitoring for cloud products and
services. Provides a reusable authorization across agencies — D1 (compliance), D6 (audit).
Newly called out in the 2024 outline. @ 00:19:28
CLOUD Act (Clarifying Lawful Overseas Use of Data Act): US law requiring cloud service providers
to produce data for investigations of serious crimes even when stored in another country —
**directly conflicts with GDPR**, which forbids transfer to countries lacking adequate protection.
No clean resolution; escalate to legal counsel. Classic "call the expert" scenario — D1. @ 00:30:15
PIPL (Personal Information Protection Law): China, effective late 2021 — D1, D2. @ 00:26:13
POPIA (Protection of Personal Information Act): South Africa, enacted 2013 — D1, D2. @ 00:26:13
CCPA (California Consumer Privacy Act): US state privacy law — D1, D2. @ 00:26:13
COPPA (Children's Online Privacy Protection Act): US federal, children's data — D1. @ 00:24:13
ECPA (Electronic Communications Privacy Act of 1986): US federal — D1. Memorize the acronym; the
Exam Cram video renders it incorrectly as "EPCA." @ 00:24:13
CALEA (Communications Assistance for Law Enforcement Act): US federal, wiretapping — D1. @ 00:24:13
HITRUST: Healthcare security framework, cited alongside HIPAA — D1, D2. @ 00:24:13
GDPR breach notification: 72-hour deadline. @ 00:32:15
FIPS 140-3: Supersedes FIPS 140-2 for NEW validation submissions as of April 1, 2022. **Both
standards define FOUR security levels** — see the conflict entry in Section A; the Addendum
states three for 140-2, which is incorrect. — D3. @ 00:42:50

---

# SECTION E — GAPS THE SOURCE DOES NOT COVER

Not additions. Recording what these two videos will NOT teach you, so their coverage is not
mistaken for complete.

Source: term-frequency analysis across both transcripts
Date: 2026-08-03

- **NIST CSF is barely covered.** Zero mentions across all 72,624 words of the 2022 course; only
  two in the Addendum, inside a brief RMF-vs-CSF comparison. Neither video enumerates the
  functions. CSF 2.0 (February 2024) added **Govern** to Identify, Protect, Detect, Respond,
  Recover. Your frameworks-map.md already has this right — the videos will not reinforce it.
- **SIEM is never mentioned in the 2022 course at all**, and appears only inside the SOAR
  discussion in the Addendum. It is also missing from your glossary. Proposed in Section B.
- **Domain 2 has no 2024 changes whatsoever** — the Addendum states it is the only domain with no
  new major or minor topics. Do not expect Addendum coverage there; the 2021/2022 material stands.
- The 2022 course predates the 2024 outline's cloud emphasis. The Addendum states cloud will
  factor "potentially substantially more" in the 2024 exam. Weight your study accordingly.
