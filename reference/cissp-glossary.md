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

ALE (Annualized Loss Expectancy): ALE = SLE × ARO. The expected monetary loss per year
from a specific threat.

SLE (Single Loss Expectancy): SLE = AV × EF. The monetary loss expected from a single
occurrence of a threat.

ARO (Annualized Rate of Occurrence): How often the threat is expected to occur per year.

AV (Asset Value): The monetary value of the asset.

EF (Exposure Factor): The percentage of asset loss caused by a threat (0 to 1).

Due Diligence: Researching and understanding risks before making decisions.

Due Care: Implementing reasonable measures to protect against known risks.

BCP (Business Continuity Plan): Strategy to ensure critical business functions continue during disruption.

DRP (Disaster Recovery Plan): Procedures to restore IT infrastructure after a disaster.

## Domain 2: Asset Security

Asset: Anything of value to the organization (data, systems, people, facilities, reputation).

Data Owner: Senior management member responsible for classifying data and defining access policy.

Data Custodian: IT/operations staff responsible for implementing the protections the owner mandates.

Data Steward: Responsible for data quality, metadata, and ensuring data use meets organizational policy.

## Domain 3: Security Architecture and Engineering

Confidentiality: Preserving authorized restrictions on information access and disclosure,
including means for protecting personal privacy and proprietary information.

Integrity: Guarding against improper information modification or destruction,
including ensuring information non-repudiation and authenticity.

Availability: Ensuring timely and reliable access to and use of information.

Defense in Depth: Layered security strategy — multiple controls at different levels.

Trusted Computing Base (TCB): The totality of protection mechanisms within a system that
enforce the security policy — hardware, firmware, and software.

## Domain 4: Communication and Network Security

VPN (Virtual Private Network): Encrypted tunnel over an untrusted network.

TLS (Transport Layer Security): Cryptographic protocol providing confidentiality and
integrity for data in transit.

## Domain 5: Identity and Access Management

Least Privilege: Users get minimum access necessary to perform their job.

Separation of Duties: No single person controls all aspects of a critical process.

Need to Know: Access restricted to what's necessary for current task (more restrictive than clearance alone).

Authentication: Verifying the identity of a user, process, or device.

Authorization: Granting or denying access rights to a resource based on identity or attributes.

Accountability: The ability to trace actions to the entity that performed them (requires authentication + audit logs).

## Domain 6: Security Assessment and Testing

Vulnerability Assessment: Identifying and quantifying security vulnerabilities in a system.

Penetration Testing: Authorized simulated attack to evaluate the security of a system.

## Domain 7: Security Operations

RPO (Recovery Point Objective): Maximum tolerable data loss measured in time.

RTO (Recovery Time Objective): Maximum tolerable downtime.

MTBF (Mean Time Between Failures): Average time between system failures.

MTTR (Mean Time To Repair): Average time to restore after failure.

Incident Response: The organized approach to addressing and managing the aftermath of a
security breach or cyberattack.

Chain of Custody: Documentation of who handled evidence, when, and what they did with it —
required for legal admissibility.

## Domain 8: Software Development Security

SDLC (Software Development Life Cycle): The structured process for planning, creating,
testing, and deploying software.

OWASP Top 10: Regularly updated list of the most critical web application security risks.

Input Validation: Verifying that all user-supplied data meets expected format before processing —
primary defense against injection attacks.
