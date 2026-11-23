# Lab Profiles & Verification Archetypes

Use these archetypes during Phase 1 to design concrete `Done check` criteria for any IT subject. Combine archetypes freely when a topic spans multiple disciplines. Never restrict the curriculum to a fixed list of technologies.

## Archetype A: Markdown Technical Books

- **Best for:** Multi-chapter technical books, structured courses, and long-form engineering guides.
- **Chapter selection:** List all detected chapters during onboarding. Ask the user which chapters belong in `Goal 1` and place the rest under `Optional`.
- **Automatic sub-level splitting:** Split dense or long chapters into focused sub-levels (`Level 2.1`, `Level 2.2`, `Level 2.3`). Keep each sub-level to one core mechanism.
- **Done check design:**
  - Apply the chapter's rule to a brand-new small scenario.
  - Spot and fix a deliberate flaw in a short snippet, config, or architectural claim.
  - Never use "summarize the chapter" or "list the main points" as a `Done check`.

## Archetype B: Technical Docs, Tools & Configuration

- **Best for:** CLI tools, DevOps utilities, editors, frameworks, APIs, and configuration-driven systems.
- **Lab pattern:** Real CLI execution, minimal config authoring, or dry-run inspection.
- **Done check design:**
  - Write a minimal valid configuration file from scratch without unused keys.
  - Predict precedence or override outcomes across global, project, and environment scopes.
  - Run a real CLI command and verify the exact flag behavior or output.

## Archetype C: Code, Algorithms & Software Engineering

- **Best for:** Programming languages, data structures, design patterns, testing, and debugging.
- **Lab pattern:** Small isolated files, unit tests, or REPL/interpreter runs.
- **Done check design:**
  - Write or fix a focused function (typically 5-25 lines) targeting one invariant.
  - Trace exact variable state across 3-4 iterations or call frames.
  - Pass a concrete test case, including one edge case.

## Archetype D: Systems, Infrastructure & Architecture Flows

- **Best for:** Operating systems, networking, databases, containers, cloud, and distributed systems.
- **Lab pattern:** Real logs, packet/process traces, container or local service inspection, or architecture scenarios.
- **Done check design:**
  - Trace an end-to-end request, packet, process, or state transition across components.
  - Diagnose a root cause from real logs, metrics, or command output.
  - Justify one concrete architecture trade-off using real constraints (latency, consistency, failure modes).

## Archetype E: Technical Analysis, Auditing & Security

- **Best for:** Reverse engineering, binary analysis, vulnerability auditing, forensics, and defensive security.
- **Strict safety guardrail:**
  - Perform **static analysis first** (reading disassembly, strings, headers, source, or logs).
  - **Never** execute untrusted binaries, scripts, or payloads outside an isolated VM or sandbox.
  - If the user has no isolated environment, keep verification strictly read-only and static.
- **Done check design:**
  - Read a real artifact, trace, or disassembly block and predict exact runtime behavior.
  - Identify a specific flaw, trust boundary, or control-flow condition with line or offset evidence.

## Archetype F: Open / Hybrid IT Domain & Verified Official-Docs Mode

- **Best for:** Cross-disciplinary projects (for example, an app combining CLI config, code, and networking) or empty-workspace sessions using verified official documentation.
- **Hybrid composition:** Pair two archetypes per level when needed (for example, Archetype B for tool setup + Archetype C for verification code). Keep each level's `Done check` to one primary skill.
- **Verified Official-Docs Mode (empty workspace):**
  - Confirm the user chose official-docs mode during the Phase 1 empty-folder gate.
  - Ground every rule, flag, and API signature in verified official documentation before writing a level or answering a turn.
  - Record the official doc URL or section title in the `CURRICULUM.md` source field for each level.
  - If an official source cannot be verified, state that explicitly instead of guessing.
