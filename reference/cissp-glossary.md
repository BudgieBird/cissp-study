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

BCP (Business Continuity Plan): Strategy to ensure critical business functions continue during disruption.

DRP (Disaster Recovery Plan): Procedures to restore IT infrastructure after a disaster.

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

Zero Trust Architecture: Security model that assumes no implicit trust based on network location.
Every access request is fully authenticated, authorized, and encrypted regardless of origin.
Core principle: "never trust, always verify."

Ephemeral Keys: Cryptographic keys generated for a single session and discarded after use.
Provides forward secrecy — compromise of long-term keys cannot decrypt past sessions.

Key Stretching: Techniques (PBKDF2, bcrypt, scrypt) that make brute-force attacks on passwords
computationally expensive by increasing the time/resources needed to derive the key.

Tokenization: Replacing sensitive data with a non-sensitive placeholder (token) that maps back
to the original data in a secure lookup table. Unlike encryption, the token has no mathematical
relationship to the original data.

## Domain 4: Communication and Network Security

VPN (Virtual Private Network): Encrypted tunnel over an untrusted network.

TLS (Transport Layer Security): Cryptographic protocol providing confidentiality and
integrity for data in transit.

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
