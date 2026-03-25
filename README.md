<p align="center">
  <h1 align="center">CISSP Study System</h1>
  <p align="center">
    An adaptive CISSP exam preparation environment built on Claude Code.<br />
    No application code — just structured reference files, AI-powered skills,<br />
    and progress tracking that work together as a personalized tutoring system.
  </p>
</p>

> [!IMPORTANT]
> This system requires [Claude Code](https://claude.ai/code) to function. The skills and commands are Claude Code primitives — they do not run as standalone scripts or applications.

<p align="center">
  <a href="https://github.com/BudgieBird/cissp-study/issues"><img alt="GitHub Issues" src="https://img.shields.io/github/issues/BudgieBird/cissp-study?color=0088ff" /></a>
  <a href="https://github.com/BudgieBird/cissp-study/pulls"><img alt="GitHub Pull Requests" src="https://img.shields.io/github/issues-pr/BudgieBird/cissp-study?color=0088ff" /></a>
  <a href="https://github.com/BudgieBird/cissp-study/graphs/contributors"><img alt="GitHub Contributors" src="https://img.shields.io/github/contributors/BudgieBird/cissp-study" /></a>
  <a href="https://github.com/BudgieBird/cissp-study/commits/main"><img alt="Last Commit" src="https://img.shields.io/github/last-commit/BudgieBird/cissp-study" /></a>
</p>

<p align="center">
  <a href="https://github.com/BudgieBird/cissp-study/releases">Releases</a>
  &middot;
  <a href="https://github.com/BudgieBird/cissp-study/issues/new">Report Bug</a>
  &middot;
  <a href="https://github.com/BudgieBird/cissp-study/issues/new">Request Feature</a>
</p>

---

## Table of Contents

- [About](#about)
- [How It Works](#how-it-works)
- [Project Structure](#project-structure)
- [Commands](#commands)
- [Skills](#skills)
- [Reference Files](#reference-files)
- [Daily Workflow](#daily-workflow)
- [Study Timeline](#study-timeline)
- [Getting Started](#getting-started)
- [Customization](#customization)
- [Current Exam Format](#current-exam-format)
- [Limitations](#limitations)
- [Contributing](#contributing)

---

## About

The CISSP exam is not a technical exam — it tests whether you can **think like a security manager**. Most IT veterans fail not because they lack knowledge, but because they answer with technical solutions instead of management-level decisions.

This system is built to address that gap. It uses schema theory to map CISSP concepts onto your existing professional knowledge through targeted analogies, then progressively shifts your thinking toward the managerial perspective the exam demands.

The entire system runs inside Claude Code. There is no web app, no database, no build step. You clone the repo, customize your profile, and start studying.

## How It Works

```
/reference/*.md  <--  ground truth (skills read these before every response)
       ^
       |  /research updates reference files with new findings
       |
  Skills (tutor, exam, validator, comprehension)
       |
       v
/progress/*.md   <--  quiz scores and weekly reviews (exam skill appends here)
```

**Skills** are Claude Code AI agents, each with a specific role and assigned model. **Commands** are slash-command wrappers that activate skills with user arguments. **Reference files** are the single source of truth — when Claude's training data conflicts with a reference file, the file wins.

The exam skill reads your past scores from `/progress/daily-scores.md` and weights future question sets toward your weak domains. The `/review` command analyzes score trends and adjusts your study plan.

## Project Structure

```
cissp-study/
|
|-- .claude/
|   |-- commands/                    # Slash command definitions
|   |   |-- study.md                 #   /study [topic]
|   |   |-- quiz.md                  #   /quiz [topic|20|full]
|   |   |-- research.md              #   /research [topic]
|   |   |-- validate.md              #   /validate [claim]
|   |   |-- rapid-fire.md            #   /rapid-fire [topic]
|   |   +-- review.md                #   /review
|   |
|   +-- skills/                      # Claude AI skill implementations
|       |-- cissp-tutor/             #   Schema-based teaching (Opus)
|       |-- cissp-exam/              #   Question generation + grading (Haiku)
|       |-- cissp-research/          #   Web search deep dives (Sonnet)
|       |-- cissp-comprehension/     #   Socratic probing (Sonnet)
|       +-- cissp-validator/         #   Fact-checking against references (Opus)
|
|-- reference/                       # Ground truth -- authoritative CISSP content
|   |-- cissp-glossary.md            #   (ISC)2 definitions by domain
|   |-- cissp-domains.md             #   8 domains, subtopics, key concepts, frameworks
|   |-- exam-traps.md                #   Known exam traps and misconceptions
|   |-- analogy-map.md.example       #   Template for background-specific analogies
|   +-- frameworks-map.md            #   NIST, ISO, OWASP, GDPR, HIPAA, SOX, PCI DSS, FIPS
|
|-- progress/                        # Performance tracking (auto-populated)
|   |-- daily-scores.md.example      #   Template for quiz/exam score logging
|   +-- weekly-reviews.md.example    #   Template for weekly analysis
|
|-- CLAUDE.md.example                # Template -- copy to CLAUDE.md and customize
+-- .gitignore                       # Keeps personal files out of version control
```

> [!NOTE]
> Files ending in `.example` are templates. The actual `CLAUDE.md`, `reference/analogy-map.md`,
> and `progress/*.md` files are in `.gitignore` so your personal data never gets committed.
> See [Getting Started](#getting-started) for setup.

## Commands

| Command | Purpose | Typical Duration |
|---|---|---|
| `/study [topic]` | Start a tutor session with 4-part format: definition, analogy, scenario, comprehension check | 45-60 min |
| `/research [topic]` | Deep-dive research using web search; updates reference files | 15 min |
| `/quiz [topic\|20\|full]` | Generate practice exam questions, grade, and log scores | 20 min |
| `/rapid-fire [topic]` | Quick definition/concept recall drilling | 10 min |
| `/validate [claim]` | Fact-check a claim against reference files | As needed |
| `/review` | Analyze weekly scores, identify trends, adjust study plan | Sundays |

The comprehension skill is triggered conversationally by saying **"Challenge me on [concept]"** rather than a slash command.

## Skills

Each skill runs on a specific model chosen for the task:

| Skill | Model | Role |
|---|---|---|
| `cissp-tutor` | Opus 4.6 | Schema-based teaching with analogies mapped to student background |
| `cissp-research` | Sonnet 4.6 | Web search research on domains, standards, and study materials |
| `cissp-comprehension` | Sonnet 4.6 | Socratic questioning to verify deep understanding |
| `cissp-exam` | Haiku 4.5 | Fast practice question generation and grading |
| `cissp-validator` | Opus 4.6 | Independent fact-checking against reference files |

**Why different models?** Opus handles nuanced teaching and validation where accuracy is critical. Sonnet handles research and comprehension probing. Haiku handles high-volume question generation where speed matters more than depth.

## Reference Files

All files in `/reference/` are **authoritative**. Skills read these before responding, and when Claude's training data conflicts with a reference file, the reference file wins.

| File | Contents | Tracked |
|---|---|---|
| `cissp-glossary.md` | (ISC)2 definitions organized by domain | Yes |
| `cissp-domains.md` | 8 domains with subtopics, key concepts, and applicable frameworks | Yes |
| `exam-traps.md` | Known exam traps and common misconceptions | Yes |
| `frameworks-map.md` | NIST, ISO, OWASP, GDPR, HIPAA, SOX, PCI DSS, FIPS with domain relevance | Yes |
| `analogy-map.md` | Analogy mappings for all 8 domains, customized to student background | No (personal) |

Reference files are aligned with the [official ISC2 CISSP Certification Exam Outline](https://www.isc2.org/certifications/cissp/cissp-certification-exam-outline) (effective April 15, 2024).

Skills that discover new definitions, traps, or framework references during sessions append them to the appropriate reference file automatically.

## Daily Workflow

```
STEP 1 -- RESEARCH (15 min)
  /research [domain or standard]
  Updates reference files with current information

STEP 2 -- LEARN (45-60 min)
  /study [topic]
  4-part format: Definition -> Analogy -> Scenario -> Comprehension Check
  Continues until understanding is demonstrated

STEP 3 -- PROVE (15-20 min)
  "Challenge me on [concept]"
  Socratic questioning: pass and move on, or go back to tutor

STEP 4 -- TEST (20 min)
  /quiz 20
  Timed, exam-format questions graded and logged

STEP 5 -- VALIDATE (as needed)
  /validate [claim]
  Fact-check anything that seems wrong

SUNDAY:
  /review
  Analyze the week's scores and adjust the study plan
```

## Study Timeline

| Phase | Weeks | Focus |
|---|---|---|
| Diagnostic | Week 1 | Cold `/quiz full` exam, identify 3 weakest and 3 strongest domains |
| Weakest Domains | Weeks 2-4 | Targeted study on 3 weakest domains |
| Middle Domains | Weeks 5-7 | Fill gaps in partial-knowledge domains, heavy scenario practice |
| Full Exams | Weeks 8-10 | Practice exams 3x/week, polish "think like a manager" mindset |

The timeline adapts to your actual study duration through the `/review` command.

## Getting Started

### Prerequisites

- [Claude Code](https://claude.ai/code) (CLI, desktop app, or IDE extension)
- An Anthropic API key or Claude Pro/Max subscription

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/BudgieBird/cissp-study.git
   cd cissp-study
   ```

2. Create your personal files from the templates:
   ```bash
   cp CLAUDE.md.example CLAUDE.md
   cp reference/analogy-map.md.example reference/analogy-map.md
   cp progress/daily-scores.md.example progress/daily-scores.md
   cp progress/weekly-reviews.md.example progress/weekly-reviews.md
   ```

3. Edit `CLAUDE.md` and fill in the **Student Profile** section with your actual background. Be specific — the tutor, comprehension, and exam skills all read this profile to tailor their responses.

4. Edit `reference/analogy-map.md` to match your professional background. The included template shows the expected format with example analogies. Replace them with analogies from your own experience.

5. Open in Claude Code:
   ```bash
   claude
   ```

6. Start studying:
   ```
   /research Security and Risk Management
   /study risk management
   /quiz 20
   ```

> [!TIP]
> Your personal files (`CLAUDE.md`, `reference/analogy-map.md`, `progress/*.md`) are
> gitignored. You can `git pull` to get reference file updates without overwriting your
> profile or scores.

### First Session

If this is your first time, start with a diagnostic:

```
/quiz full
```

This generates a 150-question exam across all 8 domains. Your results establish a baseline that the system uses to weight future study sessions toward your weak areas.

## Customization

The system is designed to be forked and personalized. Personal files are gitignored so you can pull upstream updates without merge conflicts.

**`CLAUDE.md`** (copied from `CLAUDE.md.example`)

Your student profile. Replace the placeholder values with your actual background. Be specific — the more detail you provide about your experience and tools, the better the analogies and explanations will be tailored to you. Every skill reads this file.

**`reference/analogy-map.md`** (copied from `reference/analogy-map.md.example`)

Maps CISSP concepts to analogies drawn from your professional background. The tutor skill reads this before every response. The included template shows the expected format — replace the example analogies with ones that match your experience.

**What NOT to customize:** The shared reference files (`cissp-glossary.md`, `cissp-domains.md`, `exam-traps.md`, `frameworks-map.md`) contain exam-accurate content aligned with the official ISC2 outline. These are tracked in git. Edit them only to correct inaccuracies or add new content — do not remove existing entries. If you find an error, consider opening a pull request so everyone benefits.

## Current Exam Format

> [!WARNING]
> The CISSP exam format changes periodically. Always verify against the [official ISC2 exam outline](https://www.isc2.org/certifications/cissp/cissp-certification-exam-outline) before sitting for the exam.

| Parameter | Value |
|---|---|
| Format | Computerized Adaptive Testing (CAT) |
| Questions | 100-150 (adaptive -- stops when pass/fail is determined) |
| Time | 3 hours |
| Passing Score | 700 / 1000 (scaled, not a simple percentage) |
| Effective Date | April 15, 2024 |

### 8 Domains (weighted)

| Domain | Weight |
|---|---|
| 1. Security and Risk Management | 16% |
| 2. Asset Security | 10% |
| 3. Security Architecture and Engineering | 13% |
| 4. Communication and Network Security | 13% |
| 5. Identity and Access Management | 13% |
| 6. Security Assessment and Testing | 12% |
| 7. Security Operations | 13% |
| 8. Software Development Security | 10% |

## Limitations

**Validator same-family limitation.** The validator skill runs on the same model family (Anthropic) as the tutor. When validator confidence is low (reference files insufficient), cross-validate with a non-Anthropic model or official (ISC)2 sources.

**Not a replacement for official study materials.** This system supplements — it does not replace — the (ISC)2 Official Study Guide, practice exams from authorized providers, or instructor-led training.

**Reference files can become outdated.** ISC2 periodically updates the exam outline, domain weights, and tested concepts. Run `/research` regularly and verify reference files against the [official exam outline](https://www.isc2.org/certifications/cissp/cissp-certification-exam-outline).

## Contributing

Contributions are welcome — particularly corrections to reference files, new exam traps, and improved analogy mappings for different professional backgrounds.

1. Fork the repository
2. Create a feature branch (`git checkout -b fix/update-domain-3-subtopics`)
3. Commit your changes
4. Open a pull request

If you find an inaccuracy in the reference files, please [open an issue](https://github.com/BudgieBird/cissp-study/issues/new) with a link to the authoritative source.

---

<p align="center">
  Built with <a href="https://claude.ai/code">Claude Code</a>
</p>
