TRAP 1 — Think Like a Manager
CISSP tests at a management level. The technically correct answer is often WRONG
if a more process/risk-oriented answer exists. "What should the security manager
recommend?" not "What command do you run?"

TRAP 2 — Protect Life First
In any scenario involving safety, human life is ALWAYS the top priority.
Before assets, before data, before uptime.

TRAP 3 — Due Diligence vs. Due Care
Due diligence = RESEARCH (investigate, assess, understand the risk before acting).
Due care = ACTION (implement reasonable measures to protect against known risks).
"Diligence is the homework. Care is doing the work."

TRAP 4 — Data Owner vs. Data Custodian
Owner = senior management who CLASSIFIES and decides policy.
Custodian = IT/ops who IMPLEMENTS the protection controls.
Owner decides WHAT protection. Custodian implements HOW.
Students constantly reverse these.

TRAP 5 — BCP vs. DRP
BCP = keep the business RUNNING during a disruption (broader, strategic).
DRP = restore IT systems AFTER a disruption (narrower, tactical).
BCP contains DRP. Not the other way around.

TRAP 6 — RPO vs. RTO
RPO = how much DATA LOSS is tolerable (measured backward from the incident).
RTO = how much DOWNTIME is tolerable (measured forward from the incident).
RPO answers "how old can my backup be?" RTO answers "how fast do I need to recover?"

TRAP 7 — Quantitative vs. Qualitative Risk Analysis
Quantitative = NUMBERS (ALE, SLE, ARO, dollar values).
Qualitative = JUDGMENT (high/medium/low, expert opinion, matrices).
Quantitative is more objective but harder/costlier. Qualitative is faster but subjective.
ALE = SLE × ARO. SLE = AV × EF. Students mix up the formulas.

TRAP 8 — Symmetric vs. Asymmetric Encryption
Symmetric = one shared key, FAST, for bulk data (AES).
Asymmetric = key pair (public/private), SLOW, for key exchange and signatures (RSA, ECC).
In practice you use asymmetric to exchange the symmetric key, then symmetric for the data.
Students confuse which is used for what.

TRAP 9 — Authentication Factors
Something you KNOW (password), something you HAVE (token/phone), something you ARE (biometric).
MFA requires at least TWO DIFFERENT factors. Two passwords is NOT MFA (both are "know").

TRAP 10 — Incident Response Order
ISC2's 7-step model: (1) Detection → (2) Response → (3) Mitigation → (4) Reporting →
(5) Recovery → (6) Remediation → (7) Lessons Learned
NIST 800-61 uses a different 4-phase model (Preparation → Detection/Analysis →
Containment/Eradication/Recovery → Post-Incident Activity). Know BOTH — but for
"best answer" on the CISSP, use ISC2's terminology unless the question cites NIST.
Students want to jump straight to fixing things. Mitigate/contain FIRST.

TRAP 11 — Legal Concepts
Students from technical backgrounds often bomb the legal questions.
Key distinctions: criminal vs. civil vs. regulatory, jurisdiction matters,
privacy laws vary by country (GDPR, HIPAA, etc.), evidence admissibility
requires proper chain of custody.

TRAP 12 — Bell-LaPadula vs. Biba
Bell-LaPadula = CONFIDENTIALITY (no read up, no write down — protects secrets).
Biba = INTEGRITY (no write up, no read down — protects accuracy).
Clark-Wilson = INTEGRITY through well-formed transactions and separation of duties.
Students constantly flip Bell-LaPadula and Biba.

TRAP 13 — CAT Exam Behavior
The exam is adaptive. If you're getting harder questions, that's GOOD — it means
you're performing above the threshold. It stops at 100 if it's confident in
pass/fail. Going to 150 questions means the algorithm was unsure, NOT that you're failing.

TRAP 14 — BIA vs. Risk Assessment
BIA (Business Impact Analysis) identifies CRITICAL BUSINESS FUNCTIONS and the IMPACT
of disruption (financial, operational, reputational). It answers: "What happens if this
process stops?" and drives recovery priorities (RPO/RTO).
Risk Assessment identifies THREATS, VULNERABILITIES, and LIKELIHOOD of occurrence.
It answers: "What could go wrong and how likely is it?"
BIA feeds into BCP. Risk Assessment feeds into risk treatment decisions.
Students confuse them because both "analyze" things. BIA = impact of loss.
Risk Assessment = likelihood and consequence of threats.

TRAP 15 — Unscored Pretest Items
The exam includes unscored research questions mixed in with scored ones. You CANNOT
tell which are which. Some questions will feel unusually hard or ambiguous — these may
be pretest items being evaluated for future exams. Do not let them shake your
confidence or waste disproportionate time. Treat every question the same, answer your
best, and move on.
