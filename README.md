# socratic-mentor

A universal Agent Skill that turns your AI coding assistant into a disciplined Socratic mentor for any IT domain—from local Markdown books and codebases to empty study folders backed by verified official documentation.

Instead of dumping answers, `socratic-mentor` guides you through one concept at a time with ASCII diagrams, plain-language explanations, and a progressive 1–5 hint ladder, while maintaining a clean, Obsidian-ready study plan in your workspace.

## Key Features

- **Any IT Domain:** Works across software engineering, networking, Linux, DevOps, security, databases, cloud, and AI tooling.
- **Dynamic User Language:** Automatically responds and generates study artifacts in the user's language (for example, `STUDY_PLAN.md` in English or `PLAN_ESTUDIO.md` in Spanish).
- **Two-Phase Architecture:** Separates the reusable global teaching engine from lightweight, per-workspace study state.
- **Book Chapter Selection & Sub-Level Splitting:** Lets you pick a focused subset of chapters for Goal 1 and splits dense chapters into digestible sub-levels (`Level 2.1`, `Level 2.2`).
- **Empty-Folder Verification:** When a workspace has no local materials, verifies official documentation sources before building the curriculum.
- **Prior-Level Calibration & Topic Skipping:** Assesses your starting level (`zero`, `basic`, or `intermediate`) and moves already-known topics into a collapsible `Optional` section you can unlock anytime.
- **ASD-STE100 Clarity & 1–5 Hint Ladder:** Uses short, active-voice sentences, ASCII mental models, and graduated hints so you solve core challenges yourself.
- **Obsidian-Ready Plans:** Generates clean Markdown with YAML frontmatter, relative links, checkboxes, collapsible `> [!note]-` callouts, and a session log table—without touching existing files.
- **Local Skill Deference:** Automatically defers if the current project defines a specialized local mentor skill.

## How It Works: Two-Phase Workflow

```text
+-------------------------------------------------------------------+
|               GLOBAL ENGINE (installed once)                      |
|   SKILL.md  +  references/pedagogy.md  +  references/lab-profiles |
+---------------------------------+---------------------------------+
                                  |
                                  v
              +-------------------+-------------------+
              |                                       |
              v                                       v
+---------------------------+           +---------------------------+
|   PHASE 1: SETUP          |           |   PHASE 2: MENTORING      |
|---------------------------|           |---------------------------|
| 1. Inspect workspace      |           | 1. Load local state files |
| 2. Calibrate prior level  | --------> | 2. Teach 1 core concept   |
| 3. Pick Goal 1 scope      |           | 3. Draw ASCII model       |
| 4. Split dense chapters   |           | 4. Pose Socratic challenge|
| 5. Generate local state   |           | 5. Apply 1-5 hint ladder  |
+-------------+-------------+           | 6. Update progress & log  |
              |                         +-------------+-------------+
              v                                       |
+-----------------------------------------------------+-------------+
|                LOCAL STATE (inside your workspace)                |
|        STUDY_PLAN.md (or localized)  +  CURRICULUM.md             |
|        (existing notes and source files remain untouched)         |
+-------------------------------------------------------------------+
```

## Installation

Clone the repository directly into your agent's global or project-level skills directory.

### Antigravity

- **Global:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git ~/.gemini/config/skills/socratic-mentor
  ```
- **Project-level:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git .agents/skills/socratic-mentor
  ```

### OpenCode

- **Global:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git ~/.config/opencode/skills/socratic-mentor
  # Alternative cross-agent global path:
  # git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git ~/.agents/skills/socratic-mentor
  ```
- **Project-level:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git .opencode/skills/socratic-mentor
  # Alternative cross-agent project path:
  # git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git .agents/skills/socratic-mentor
  ```

### Claude Code

- **Global:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git ~/.claude/skills/socratic-mentor
  ```
- **Project-level:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git .claude/skills/socratic-mentor
  ```

### Other Agent Skills-Compatible Tools (Codex, Cursor, etc.)

- **Global:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git ~/.agents/skills/socratic-mentor
  ```
- **Project-level:**
  ```bash
  git clone https://github.com/CarlosLopez-Ciber/socratic-mentor.git .agents/skills/socratic-mentor
  ```

## Quick-Start Prompts

Open your study folder (a Markdown book, a docs folder, a codebase, or an empty folder) and start a session in your preferred language.

**English:**

```text
Guide me through this folder using the Socratic method. No spoilers—only hints.
```

```text
I want to learn Docker networking from scratch in this empty folder. Be my Socratic mentor and set up a study plan.
```

**Spanish (automatic language matching):**

```text
Guíame por este libro con el método socrático. Sin spoilers, solo pistas.
```

```text
Quiero aprender redes en Linux desde cero en esta carpeta vacía. Sé mi mentor socrático y crea el plan de estudio.
```

## Repository Layout

```text
socratic-mentor/
├── SKILL.md                         # Core two-phase skill instructions and rules
├── references/
│   ├── pedagogy.md                  # ASD-STE100 clarity rules, ASCII diagrams, 1-5 hint ladder
│   └── lab-profiles.md              # Universal IT verification archetypes (books, docs/CLI, code, systems, security, official docs)
├── resources/
│   ├── STUDY_PLAN.tmpl.md           # Obsidian-ready study plan template
│   └── CURRICULUM.tmpl.md           # Structured per-level curriculum template
├── examples/
│   └── example-markdown-book.md     # Sanitized example for a multi-chapter Markdown book
├── README.md                        # Documentation and installation guide
├── LICENSE                          # MIT License
└── .gitignore                       # Ignores OS metadata, secrets, and generated study state
```

## License

This project is licensed under the [MIT License](./LICENSE).
