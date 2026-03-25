# CISSP Glossary — (ISC)² Key Definitions by Domain

## Domain 1: Security and Risk Management

Risk: The likelihood that a threat will exploit a vulnerability to cause harm to an asset.

Threat: Any circumstance or event with the potential to adversely impact organizational
operations, assets, or individuals through unauthorized access, destruction, disclosure,
modification of information, or denial of service.

Vulnerability: A weakness in a system, system security procedures, internal controls,
or implementation that could be exploited.

Control (Safeguard/Countermeasure): A measure taken to reduce risk. Can be administrative
(policy), technical (firewall), or physical (locks).

ALE (Annualized Loss Expectancy): ALE = SLE x ARO. The expected monetary loss per year
from a specific threat.

SLE (Single Loss Expectancy): SLE = AV x EF. The monetary loss expected from a single
occurrence of a threat.

ARO (Annualized Rate of Occurrence): How often the threat is expected to occur per year.

AV (Asset Value): The monetary value of the asset.

EF (Exposure Factor): The percentage of asset loss caused by a threat (0 to 1).

Due Diligence: Researching and understanding risks before making decisions.

Due Care: Implementing reasonable measures to protect against known risks.

BIA (Business Impact Analysis): Process that identifies critical business functions and
quantifies the impact of their disruption (financial, operational, reputational). Drives
recovery priorities — determines RPO and RTO for each function. BIA feeds into BCP. Not
the same as risk assessment: BIA = "what happens if we lose this?" Risk assessment =
"what could go wrong and how likely?"

BCP (Business Continuity Plan): Strategy to ensure critical business functions continue during disruption.

DRP (Disaster Recovery Plan): Procedures to restore IT infrastructure after a disaster.

Threat Modeling: Structured approach to identifying and prioritizing threats to a system.
Methodologies: STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial
of service, Elevation of privilege — developed by Microsoft). DREAD (Damage, Reproducibility,
Exploitability, Affected users, Discoverability — risk rating model). PASTA (Process for
Attack Simulation and Threat Analysis — 7-stage risk-centric methodology). Attack trees
(hierarchical diagrams showing paths to achieve an attack goal).

Risk Appetite: The level of risk an organization is willing to accept in pursuit of its objectives.
Set by senior management/board.

Risk Tolerance: The acceptable variation from risk appetite. More granular — how much deviation
from the target risk level is permissible.

Risk Capacity: The maximum amount of risk an organization can absorb before it threatens viability.

Supply Chain Risk Management (SCRM): Identifying, assessing, and mitigating risks associated
with third-party vendors, suppliers, and service providers in the supply chain.

Security Governance: The set of responsibilities and practices exercised by the board and
executive management to provide strategic direction, ensure objectives are achieved, manage
risk appropriately, and verify that resources are used responsibly.

Security Management: The day-to-day operational implementation of security controls as
directed by governance. Governance decides; management executes.

## Domain 2: Asset Security

Asset: Anything of value to the organization (data, systems, people, facilities, reputation).

Data Owner: Senior management member responsible for classifying data and defining access policy.

Data Custodian: IT/operations staff responsible for implementing the protections the owner mandates.

Data Steward: Responsible for data quality, metadata, and ensuring data use meets organizational policy.

Data Controller (GDPR): The entity that determines the purposes and means of processing
personal data. Decides WHY and HOW data is processed. Bears primary compliance responsibility.

Data Processor (GDPR): The entity that processes personal data on behalf of the controller.
Follows the controller's instructions. Must still comply with security obligations.

Data Subject: The individual whose personal data is being collected, stored, or processed.

Data Remanence: Residual data remaining on storage media after deletion. Standard file deletion
does not remove data — it removes pointers. Requires sanitization (overwrite, degauss, or destroy).

Scoping: Determining which portions of a standard or framework apply to a specific system or environment.

Tailoring: Customizing selected controls to fit the specific needs of the organization or system.

## Domain 3: Security Architecture and Engineering

Confidentiality: Preserving authorized restrictions on information access and disclosure,
including means for protecting personal privacy and proprietary information.

Integrity: Guarding against improper information modification or destruction,
including ensuring information non-repudiation and authenticity.

Availability: Ensuring timely and reliable access to and use of information.

Defense in Depth: Layered security strategy — multiple controls at different levels.

Trusted Computing Base (TCB): The totality of protection mechanisms within a system that
enforce the security policy — hardware, firmware, and software.

Security Kernel: The hardware, firmware, and software elements of a TCB that implement
the reference monitor concept. Must be tamperproof, always invoked, and small enough to be verified.

Reference Monitor: An abstract machine that mediates all access subjects have to objects,
checking authorization against the security policy.

Star Model (*-Property): The write restriction component of formal security models. In
Bell-LaPadula, the *-property = "no write down" (prevents leaking classified data to lower
clearance levels). In Biba, the *-integrity axiom = "no write up" (prevents contaminating
higher-integrity data). ISC2 lists Star Model as a standalone exam outline item.

Brewer-Nash Model (Chinese Wall): Dynamic access control model that prevents conflicts of
interest. Once a subject accesses data in one conflict-of-interest class (e.g., Company A's
financials), access to competing datasets in the same class (e.g., Company B's financials)
is denied. Access restrictions change based on what has already been accessed. Common in
financial services, legal firms, and consulting.

Zero Trust Architecture: Security model that assumes no implicit trust based on network location.
Every access request is fully authenticated, authorized, and encrypted regardless of origin.
Core principle: "never trust, always verify."

Ephemeral Keys: Cryptographic keys generated for a single session and discarded after use.
Provides forward secrecy — compromise of long-term keys cannot decrypt past sessions.

TCSEC (Trusted Computer System Evaluation Criteria / Orange Book): US DoD standard for
evaluating computer security. Defines divisions: D (minimal), C1/C2 (discretionary), B1/B2/B3
(mandatory), A1 (verified). Replaced by Common Criteria but still tested on CISSP for historical
context and conceptual understanding.

ITSEC (Information Technology Security Evaluation Criteria): European security evaluation
standard. Separated functionality from assurance (unlike TCSEC which combined them).
Precursor to Common Criteria.

Common Criteria (ISO/IEC 15408): International standard for IT security evaluation. Uses
Evaluation Assurance Levels (EAL1-EAL7). EAL1 = functionally tested, EAL4 = methodically
designed/tested/reviewed (typical commercial target), EAL7 = formally verified. Products
evaluated against a Protection Profile (PP) or Security Target (ST).

EAL (Evaluation Assurance Level): Scale from EAL1 (lowest) to EAL7 (highest) in Common
Criteria. Higher EAL = more rigorous evaluation, not necessarily more secure product. EAL4
is the highest level practically achievable without specialized development techniques.

Protection Profile (PP): Common Criteria document specifying security requirements for a
class of products (e.g., "all firewalls must meet these requirements"). Written by consumers
or communities of interest, not vendors.

Security Target (ST): Common Criteria document specifying security claims for a specific
product. Written by the vendor. Evaluated against a Protection Profile.

PKI (Public Key Infrastructure): Framework for managing digital certificates and public keys.
Components: Certificate Authority (CA), Registration Authority (RA), Certificate Revocation
List (CRL), Online Certificate Status Protocol (OCSP), certificate repository.

Certificate Authority (CA): Trusted entity that issues, signs, and revokes digital certificates.
Root CA sits at top of trust hierarchy. Subordinate/intermediate CAs issue end-entity certificates.

Registration Authority (RA): Verifies the identity of certificate requestors before the CA
issues the certificate. Handles identity proofing — does NOT sign certificates itself.

CRL (Certificate Revocation List): Published list of certificates that have been revoked before
their expiration date. Checked by relying parties. Disadvantage: may not be current between
publication intervals.

OCSP (Online Certificate Status Protocol): Real-time certificate status checking. Client queries
OCSP responder for current status of a specific certificate. More current than CRLs but requires
the responder to be available.

Certificate Pinning: Associating a specific certificate or public key with a host, bypassing
the normal certificate chain validation. Prevents MITM attacks using rogue CA-issued certificates.

Key Escrow: Storage of cryptographic keys by a trusted third party. Enables key recovery if
the original key holder is unavailable. Controversial — creates a single point of compromise.

Key Stretching: Techniques (PBKDF2, bcrypt, scrypt) that make brute-force attacks on passwords
computationally expensive by increasing the time/resources needed to derive the key.

Tokenization: Replacing sensitive data with a non-sensitive placeholder (token) that maps back
to the original data in a secure lookup table. Unlike encryption, the token has no mathematical
relationship to the original data.

Covert Channel: Unauthorized communication path that violates security policy. Covert storage
channel: one process signals another by modifying a shared storage location (e.g., file lock
status, disk space). Covert timing channel: one process signals another by modulating system
resource timing (e.g., CPU usage patterns). Harder to detect than storage channels.

Trusted Recovery: System's ability to recover to a secure state after failure. Manual recovery:
administrator intervention required — system halts in a secure state. Automated recovery:
system recovers to secure state without admin help. Automated recovery without undue loss:
system recovers while preserving maximum data. Function recovery: more complex — recovers
specific functions in priority order.

TEMPEST: US government program for studying and controlling electronic emanations from
equipment. Compromising emanations can be intercepted to reconstruct data. Countermeasures
include Faraday cages, shielded cables, and white noise generators.

## Domain 4: Communication and Network Security

VPN (Virtual Private Network): Encrypted tunnel over an untrusted network.

TLS (Transport Layer Security): Cryptographic protocol providing confidentiality and
integrity for data in transit. TLS 1.3 is current — removed weak ciphers, reduced
handshake round trips. TLS replaced SSL (all SSL versions are deprecated and insecure).

IPsec (Internet Protocol Security): Protocol suite for securing IP communications.
Two protocols: AH (Authentication Header) = integrity + authentication only, no encryption.
ESP (Encapsulating Security Payload) = integrity + authentication + encryption. Two modes:
Transport mode = encrypts payload only (host-to-host). Tunnel mode = encrypts entire original
packet (gateway-to-gateway, used in VPNs).

Wireless Security Protocols: WEP = broken (RC4, static keys — never use). WPA = interim fix
(TKIP). WPA2 = current standard (AES-CCMP). WPA3 = latest (SAE replaces PSK handshake,
forward secrecy, stronger encryption). Enterprise mode uses 802.1X/RADIUS authentication.

802.1X: IEEE standard for port-based network access control. Uses EAP (Extensible
Authentication Protocol) between supplicant, authenticator, and authentication server (RADIUS).
Prevents unauthorized devices from connecting to the network.

Converged Protocols: Integration of specialized protocols onto standard IP networks.
Examples: FCoE (Fibre Channel over Ethernet), iSCSI (SCSI over IP), VoIP (voice over IP).
Security concern: traditional network controls must now protect previously isolated protocols.

SD-WAN (Software-Defined Wide Area Network): WAN architecture that uses software-defined
networking to manage connectivity and traffic between data centers, branches, and cloud.
Centralizes policy control over distributed infrastructure.

East-West Traffic: Network traffic between servers/services within a data center or cloud
environment (lateral movement). Contrasts with north-south traffic (client-to-server,
crossing the perimeter). Microsegmentation controls east-west traffic.

North-South Traffic: Network traffic that crosses the network perimeter — client requests
entering and server responses leaving the network boundary.

Content Distribution Network (CDN): Distributed network of proxy servers and data centers
providing high availability and performance by distributing content geographically closer to users.

## Domain 5: Identity and Access Management

Least Privilege: Users get minimum access necessary to perform their job.

Separation of Duties: No single person controls all aspects of a critical process.

Need to Know: Access restricted to what's necessary for current task (more restrictive than clearance alone).

Authentication: Verifying the identity of a user, process, or device.

Kerberos: Network authentication protocol using symmetric key cryptography and a trusted
third party (KDC). Components: Key Distribution Center (KDC) = Authentication Server (AS) +
Ticket-Granting Server (TGS). Process: (1) Client → AS: request TGT. (2) AS → Client:
response encrypted with client's secret key, containing a session key + the TGT (TGT itself
is encrypted with TGS's secret key — opaque to client). (3) Client → TGS: TGT + request for
service ticket. (4) TGS → Client: service ticket. (5) Client → Service: service ticket.
Uses timestamps to prevent replay attacks. Default ticket lifetime is typically 10 hours.
Single sign-on within a Kerberos realm.

SAML (Security Assertion Markup Language): XML-based standard for exchanging authentication
and authorization data between identity providers (IdP) and service providers (SP). Used for
web-based SSO in enterprise environments. Three assertion types: authentication, attribute,
authorization decision. SAML 2.0 is current.

OAuth 2.0: Authorization framework (NOT authentication) that allows third-party applications
to access resources on behalf of a user without sharing credentials. Issues access tokens.
Common in API authorization. Does NOT verify identity — only delegates access.

OpenID Connect (OIDC): Authentication layer built ON TOP of OAuth 2.0. Adds identity
verification via ID tokens (JWTs). Provides both authentication and authorization.
"OAuth tells you what you can do. OIDC tells you who you are."

RADIUS (Remote Authentication Dial-In User Service): Client/server protocol for centralized
authentication, authorization, and accounting (AAA). Encrypts only the password in transit.
Uses UDP. Commonly used with 802.1X.

TACACS+ (Terminal Access Controller Access-Control System Plus): Cisco-developed AAA protocol.
Encrypts the entire packet payload (more secure than RADIUS in transit). Uses TCP. Separates
authentication, authorization, and accounting into independent functions.

Authorization: Granting or denying access rights to a resource based on identity or attributes.

Accountability: The ability to trace actions to the entity that performed them (requires authentication + audit logs).

Identity Proofing: The process of verifying that a person is who they claim to be BEFORE issuing
credentials. Happens during enrollment/registration, not during login.

Type I Error (False Rejection Rate / FRR): Rejecting a legitimate user. Inconvenient.

Type II Error (False Acceptance Rate / FAR): Accepting an impostor. Dangerous.

Crossover Error Rate (CER/EER): The point where FRR equals FAR. Lower CER = more accurate
biometric system. This is the standard comparison metric for biometric systems.

Provisioning: The process of creating, managing, and maintaining user accounts and access rights
throughout the identity lifecycle (joiner-mover-leaver).

Just-In-Time (JIT) Access: Providing elevated privileges only when needed and automatically
revoking them after the task is complete. Reduces standing privilege attack surface.

Lattice-Based Access Control: Mathematical model where subjects and objects are assigned
security labels forming a lattice structure. Access decisions are based on the relationship
between subject clearance and object classification within the lattice. Underpins both
Bell-LaPadula and Biba models.

Access Control Attacks: Brute force (try all combinations), dictionary (try common passwords),
rainbow table (precomputed hash lookup — defeated by salting), pass-the-hash (use stolen hash
without cracking), Kerberoasting (request service tickets then crack offline), credential
stuffing (reuse breached credentials across sites), password spraying (try common passwords
across many accounts to avoid lockout).

## Domain 6: Security Assessment and Testing

Vulnerability Assessment: Identifying and quantifying security vulnerabilities in a system.

Penetration Testing: Authorized simulated attack to evaluate the security of a system.

Code Coverage: The percentage of source code exercised by a test suite. Higher coverage
means more code paths have been tested but does not guarantee absence of bugs.

Interface Testing: Verifying that system components interact correctly through their defined
interfaces (APIs, UIs, network interfaces). Tests data exchange, error handling, and integration points.

Misuse Case Testing: Testing from the attacker's perspective — identifying how a system can be
abused or misused. Complements positive testing (use cases) with negative scenarios.

Fuzz Testing (Fuzzing): Providing random, malformed, or unexpected input to a program to
discover vulnerabilities. Effective at finding input validation flaws, buffer overflows,
and error handling issues.

Breach Attack Simulation (BAS): Automated tools that continuously simulate real-world attack
scenarios to validate security controls are functioning as expected.

SOC 1 (Service Organization Control 1): Audit report focused on internal controls relevant
to financial reporting. Governed by SSAE 18 (Statement on Standards for Attestation
Engagements). Relevant when a service organization's controls could affect a client's
financial statements.

SOC 2 (Service Organization Control 2): Audit report evaluating controls relevant to security,
availability, processing integrity, confidentiality, and/or privacy (Trust Services Criteria).
Type I = controls at a point in time (design only). Type II = controls over a period of time
(design + operating effectiveness). Type II is more rigorous and more commonly requested.

SOC 3 (Service Organization Control 3): Public-facing summary of a SOC 2 report. Contains the
auditor's opinion but not the detailed control descriptions or test results. Suitable for
general distribution (e.g., posting on a website). Less detailed than SOC 2.

## Domain 7: Security Operations

RPO (Recovery Point Objective): Maximum tolerable data loss measured in time.

RTO (Recovery Time Objective): Maximum tolerable downtime.

MTBF (Mean Time Between Failures): Average time between system failures.

MTTR (Mean Time To Repair): Average time to restore after failure.

Incident Response: The organized approach to addressing and managing the aftermath of a
security breach or cyberattack.

Chain of Custody: Documentation of who handled evidence, when, and what they did with it —
required for legal admissibility.

Hot Site: Fully operational offsite facility with real-time data replication. Fastest recovery
(hours). Most expensive.

Warm Site: Partially equipped offsite facility with hardware and connectivity but not current data.
Recovery time: days. Moderate cost.

Cold Site: Empty facility with basic infrastructure (power, connectivity) but no equipment
or data. Recovery time: weeks. Least expensive.

RAID (Redundant Array of Independent Disks): Data storage virtualization combining multiple
physical drives for redundancy and/or performance.
- RAID 0: Striping, no redundancy (performance only)
- RAID 1: Mirroring (full redundancy, 50% capacity loss)
- RAID 5: Striping with distributed parity (survives 1 drive failure)
- RAID 6: Striping with double parity (survives 2 drive failures)
- RAID 10: Mirrored stripes (high performance + redundancy)

Journaling: Recording changes to a transaction log before committing them to the database.
Enables recovery to a consistent state after unexpected failure.

Evidence Types: Real/physical evidence (tangible objects — hard drive, printout). Documentary
evidence (documents, logs, records — subject to best evidence rule, must be original or
authenticated copy). Testimonial evidence (witness statements under oath — subject to hearsay
rule). Demonstrative evidence (illustrations, models used to explain — not direct evidence).
Best evidence rule: original documents are preferred over copies.

Evidence Admissibility Requirements: Relevant (relates to the case), sufficient (enough to
prove/disprove), reliable (collected and preserved properly), legally obtained (proper
authorization/warrant). Chain of custody must be maintained throughout.

Fire Suppression Classes: Class A = ordinary combustibles (wood, paper) — water. Class B =
flammable liquids (gasoline, oil) — CO2, foam, dry chemical. Class C = electrical equipment —
CO2, clean agent (disconnect power first). Class D = combustible metals — dry powder.
For data centers: clean agents (FM-200/HFC-227ea, Novec 1230) replaced Halon (banned by
Montreal Protocol due to ozone depletion). Water mist systems are also acceptable.

CPTED (Crime Prevention Through Environmental Design): Approach to physical security using
architectural design to reduce crime. Principles: natural surveillance (visibility), natural
access control (directional flow), territorial reinforcement (ownership cues), maintenance
(upkeep signals active monitoring).

Vestibule (Mantrap): Physical access control — small room with two interlocking doors.
Only one door can be open at a time. Prevents tailgating/piggybacking. Used at high-security
entry points.

Bollards: Physical barriers (posts) that prevent vehicle-borne attacks. Protect building
perimeters and pedestrian areas from ramming.

Faraday Cage: Enclosure of conductive material that blocks electromagnetic fields. Prevents
electronic eavesdropping (TEMPEST attacks) and wireless signal leakage. Used in SCIFs
(Sensitive Compartmented Information Facilities).

DLP (Data Loss Prevention): Controls that detect and prevent unauthorized transmission of
sensitive data outside the organization. Network DLP monitors data in transit (email, web,
FTP). Endpoint DLP monitors data on devices (USB, print, clipboard). Storage DLP scans data
at rest (file shares, databases, cloud storage). Policy-based: rules define what data cannot
leave and through which channels.

Change Management: Formal process for requesting, evaluating, approving, implementing, and
reviewing changes to IT systems. Purpose: prevent unauthorized or poorly tested changes from
causing outages or security incidents. Key elements: change request, impact assessment,
approval authority (Change Advisory Board / CAB), implementation, post-implementation review.
Emergency changes still require documentation — retroactive approval is acceptable.

Configuration Management: Process of identifying, documenting, and controlling the configuration
of IT assets throughout their lifecycle. Establishes and maintains baselines — known-good
states that can be compared against to detect drift or unauthorized changes. Configuration
Management Database (CMDB) is the authoritative record. Supports auditing, incident response,
and change management.

## Domain 8: Software Development Security

SDLC (Software Development Life Cycle): The structured process for planning, creating,
testing, and deploying software.

OWASP Top 10: Regularly updated list of the most critical web application security risks.

Input Validation: Verifying that all user-supplied data meets expected format before processing —
primary defense against injection attacks.

SAMM (Software Assurance Maturity Model): OWASP framework for measuring and improving an
organization's software security posture. Defines maturity levels across governance,
design, implementation, verification, and operations.

BSIMM (Building Security In Maturity Model): Descriptive model that measures actual software
security practices across organizations. Unlike SAMM (prescriptive), BSIMM reflects what
organizations are actually doing — useful for benchmarking.

Secure DevOps (DevSecOps): Integration of security practices into every phase of the
DevOps pipeline — plan, code, build, test, release, deploy, operate, monitor. Security
is a shared responsibility, not a phase or gate.

Software Composition Analysis (SCA): Automated identification of open-source components
and known vulnerabilities in third-party libraries within a codebase.

API Gateway: Centralized entry point for API traffic that enforces authentication, rate
limiting, input validation, and logging. Single enforcement point for API security policy.

SDLC Models: Waterfall (sequential phases — requirements, design, implementation, testing,
deployment, maintenance; rigid, no backtracking). Agile (iterative sprints, adaptive, frequent
delivery). Spiral (risk-driven, combines waterfall and prototyping — four phases per iteration:
planning, risk analysis, engineering, evaluation). RAD (Rapid Application Development —
prioritizes speed, heavy prototyping). DevOps/DevSecOps = continuous integration and delivery
with security built into the pipeline.

Database Security Concepts: Polyinstantiation = multiple instances of the same data at different
classification levels, preventing inference attacks (lower-clearance user sees different data
than higher-clearance user for the same record). Inference attack = deriving classified
information from unclassified data through correlation. Aggregation attack = combining
individual unclassified data points to derive classified information. Views = restricting which
rows/columns a user can see (content-dependent access control).

SQL Injection: Attacker inserts malicious SQL statements into input fields to manipulate the
database. Defense: parameterized queries (prepared statements), input validation, stored
procedures, least-privilege database accounts.

XSS (Cross-Site Scripting): Attacker injects malicious scripts into web pages viewed by other
users. Stored XSS (persistent — script saved in database), Reflected XSS (non-persistent —
script in URL), DOM-based XSS (client-side manipulation). Defense: output encoding, input
validation, Content Security Policy (CSP).

CSRF (Cross-Site Request Forgery): Attacker tricks authenticated user into submitting
unintended requests. The victim's browser sends the request with valid session credentials.
Defense: anti-CSRF tokens, SameSite cookie attribute, re-authentication for sensitive actions.

Software Supply Chain Security: Verifying integrity and security of third-party components.
Includes: Software Bill of Materials (SBOM) for component inventory, dependency scanning,
code signing to verify authenticity, secure build pipelines, vendor risk assessment.
