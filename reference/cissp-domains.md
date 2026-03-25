# CISSP 8 Domains — Subtopics, Key Concepts, and Frameworks

Exam: (ISC)² Certified Information Systems Security Professional (CISSP)
Format: Computerized Adaptive Testing (CAT)
Questions: 100-150 (adaptive — stops when pass/fail is determined)
Time: 3 hours maximum
Passing: 700/1000 (scaled score, but functionally pass/fail)

---

## Domain 1: Security and Risk Management (16%)

**Subtopics:**
- Professional ethics ((ISC)² Code of Professional Ethics, organizational code of ethics)
- Security concepts (confidentiality, integrity, availability, authenticity, nonrepudiation)
- Security governance principles (alignment with business strategy, organizational processes, roles and responsibilities, frameworks, due care/due diligence)
- Legal and regulatory compliance issues (privacy, intellectual property, import/export, transborder data flow)
- Investigation types and requirements (administrative, criminal, civil, regulatory)
- Security policies, standards, procedures, and guidelines
- Business continuity (BCP) requirements
- Personnel security policies and procedures
- Risk management concepts (identification, assessment, response, monitoring)
- Threat modeling concepts and methodologies
- Supply chain risk management (SCRM)
- Security awareness, education, and training programs
- Quantitative and qualitative risk analysis

**Key Concepts:**
- Risk = Threat × Vulnerability × Impact (conceptual relationship — not a calculable formula; use ALE/SLE/ARO for quantitative analysis)
- ALE = SLE × ARO, SLE = AV × EF
- Risk treatment: accept, mitigate, transfer, avoid
- Due diligence (research) vs. due care (action)
- BCP contains DRP — BCP is broader
- Life safety is always the top priority

**Applicable Frameworks:**
NIST SP 800-30, NIST SP 800-37 (RMF), NIST SP 800-53, ISO/IEC 27005, COBIT, GDPR, HIPAA, SOX

---

## Domain 2: Asset Security (10%)

**Subtopics:**
- Information and asset identification and classification
- Information and asset handling requirements
- Secure asset provisioning (assignment, transport, sanitization, disposal)
- Data lifecycle management (creation, storage, use, sharing, archival, destruction)
- Asset retention requirements (end-of-life, end-of-support)
- Data security controls and compliance requirements
- Data ownership (owner, custodian, steward)
- Privacy protection
- Data states: at rest, in transit, in use
- Data remanence and sanitization

**Key Concepts:**
- Data owner = senior management (classifies, decides policy)
- Data custodian = IT (implements protections)
- Classification levels: public, internal, confidential, restricted
- Government classification parallel: Unclassified, Confidential, Secret, Top Secret
- Data remanence: "rm" doesn't actually delete — sanitize properly

**Applicable Frameworks:**
NIST SP 800-88 (sanitization), NIST SP 800-53, ISO/IEC 27001, GDPR (data rights), PCI DSS (cardholder data)

---

## Domain 3: Security Architecture and Engineering (13%)

**Subtopics:**
- Engineering processes using secure design principles
- Security models (Bell-LaPadula, Biba, Star Model, Clark-Wilson, Brewer-Nash/Chinese Wall)
- Control selection based on information security requirements
- Information systems security capabilities (memory protection, virtualization, TPM, encryption/decryption)
- Vulnerability assessment and mitigation (architectural, design, implementation)
- Cryptographic solutions (lifecycle, methods, PKI, key management, digital signatures)
- Cryptanalytic attacks
- Site and facility design principles
- Site and facility security controls
- Information system lifecycle management (requirements, acquisition, testing, deployment, disposal)
- Trusted Computing Base (TCB) and security evaluation criteria
- Security design principles (defense in depth, least privilege, zero trust)

**Key Concepts:**
- Bell-LaPadula = confidentiality (no read up, no write down)
- Biba = integrity (no write up, no read down)
- Clark-Wilson = integrity through well-formed transactions and separation of duties
- Star Model (*-property) = the write restriction component of formal security models. In Bell-LaPadula, the *-property means "no write down" (prevents leaking secrets to lower levels). In Biba, the *-integrity axiom means "no write up" (prevents contaminating higher-integrity data). ISC2 lists Star Model separately in the exam outline.
- Brewer-Nash (Chinese Wall) = dynamic access control that prevents conflicts of interest. Once a subject accesses data in one conflict class, access to competing datasets is denied. Common in financial, legal, and consulting environments.
- Symmetric = shared key, fast, bulk data (AES)
- Asymmetric = key pair, slow, key exchange/signatures (RSA, ECC)
- Hashing = integrity verification, not encryption (SHA-256)
- Defense in depth = layered controls at every level

**Applicable Frameworks:**
NIST CSF 2.0, FIPS 140-2/3 (crypto modules), ISO/IEC 27001, Common Criteria (ISO 15408)

---

## Domain 4: Communication and Network Security (13%)

**Subtopics:**
- OSI and TCP/IP models
- Network components (firewalls, routers, switches, WAPs)
- Secure network architecture (segmentation, DMZ, zero trust)
- Secure communication channels (VPN, TLS/SSL, IPsec)
- Network attacks (MITM, replay, ARP spoofing, DNS poisoning)
- Software-defined networking (SDN) and microsegmentation
- Wireless security

**Key Concepts:**
- Stateful vs. stateless firewalls
- Network segmentation reduces blast radius
- VPN = encrypted tunnel over untrusted network
- TLS = confidentiality + integrity for data in transit
- DNSSEC = integrity for DNS responses
- Microsegmentation = pod-to-pod / service-to-service rules

**Applicable Frameworks:**
NIST SP 800-53, ISO/IEC 27033 (network security), PCI DSS (network segmentation requirements)

---

## Domain 5: Identity and Access Management (13%)

**Subtopics:**
- Physical and logical access control
- Identification and authentication of people, devices, and services
- Federated identity with third-party services
- Authorization mechanisms implementation (DAC, MAC, RBAC, ABAC, rule-based)
- Identity and access provisioning lifecycle (provisioning, review, deprovisioning)
- Authentication systems implementation (SSO, MFA, FIDO)
- Access control models (DAC, MAC, RBAC, ABAC)
- Credential management systems
- Session management

**Key Concepts:**
- MFA requires two DIFFERENT factors — two passwords is not MFA
- Least privilege = minimum access to do the job
- Need to know = more restrictive than clearance alone
- Separation of duties = prevents fraud and errors
- DAC = owner decides (Linux file permissions)
- MAC = system enforces (SELinux)
- RBAC = role-based (group memberships)
- ABAC = attribute-based (tags, context)

**Applicable Frameworks:**
NIST SP 800-63 (digital identity), NIST SP 800-53, ISO/IEC 27001, FIDO2/WebAuthn

---

## Domain 6: Security Assessment and Testing (12%)

**Subtopics:**
- Assessment, test, and audit strategy design and validation
- Security control testing (vulnerability assessments, penetration testing, SAST, DAST)
- Security process data collection (account management, management review, KPIs/KRIs)
- Test output analysis and reporting
- Security audit conduction (internal, external, third-party)
- Log reviews and audit trails
- Synthetic transactions and monitoring

**Key Concepts:**
- Vulnerability scan = find weaknesses (automated)
- Penetration test = exploit weaknesses (authorized)
- SAST = static analysis (scan code before it runs)
- DAST = dynamic analysis (scan running application)
- SOC 2 Type I = controls at a point in time
- SOC 2 Type II = controls over a period of time
- KPIs/KRIs = measure security posture quantitatively

**Applicable Frameworks:**
NIST SP 800-53A (assessment), NIST SP 800-115 (testing), OWASP Testing Guide, ISO/IEC 27001 (audit), PCI DSS (ASV scans)

---

## Domain 7: Security Operations (13%)

**Subtopics:**
- Investigation compliance and requirements (evidence handling, chain of custody)
- Logging and monitoring activities (SIEM, continuous monitoring)
- Configuration management
- Foundational security operations concepts (need-to-know, least privilege, separation of duties)
- Resource protection (media management, hardware/software asset management)
- Incident management (detection, response, containment, recovery, lessons learned)
- Detection and preventative measures (IDS/IPS, firewalls, honeypots, sandboxing)
- Patch and vulnerability management
- Change management process participation
- Recovery strategy implementation (backup, redundancy, resilience)
- Disaster recovery processes and plans
- Disaster recovery plan testing (tabletop, walkthrough, simulation, full interruption)
- Business continuity planning and exercises
- Physical security implementation and management
- Personnel safety and security concerns (travel, duress, emergency management)
- Data loss prevention (DLP)

**Key Concepts:**
- ISC2 IR phases: Detection → Response → Mitigation → Reporting → Recovery → Remediation → Lessons Learned
- NIST SP 800-61 (4-phase): Preparation → Detection/Analysis → Containment/Eradication/Recovery → Post-Incident Activity
- Contain/mitigate FIRST — stop the bleeding before surgery
- Chain of custody = evidence integrity for legal admissibility
- Forensics: image the disk first, never write to the original
- RPO = tolerable data loss (backward from incident)
- RTO = tolerable downtime (forward from incident)
- MTBF = average time between failures
- MTTR = average time to restore

**Applicable Frameworks:**
NIST SP 800-61 (incident handling), NIST SP 800-137 (continuous monitoring), NIST SP 800-88 (media sanitization), ISO/IEC 27035 (incident management), ITIL (service management)

---

## Domain 8: Software Development Security (10%)

**Subtopics:**
- SDLC and secure development methodologies
- Security controls in development environments
- Software security effectiveness
- Secure coding guidelines
- Software supply chain security
- API security
- Acquired software security impact

**Key Concepts:**
- Security must be built IN to SDLC, not bolted on after
- OWASP Top 10 = most critical web app security risks
- SQL injection = unsanitized input executed by database
- XSS = malicious script injected into web pages
- Input validation = primary defense against injection attacks
- Software supply chain = trust verification for dependencies
- DevSecOps = security scanning integrated into CI/CD pipeline

**Applicable Frameworks:**
OWASP Top 10, OWASP SAMM, NIST SP 800-53, NIST SSDF (Secure Software Development Framework), ISO/IEC 27034 (application security)
