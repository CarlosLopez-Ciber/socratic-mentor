# Curriculum: <Course or Topic Title>

<!--
Template note for the agent:
Localize all headings, field labels, and the generated filename into the user's language
(for example: CURRICULUM.md in English, CURRICULO.md in Spanish).
Keep every Core concept concrete enough to draw in an ASCII diagram.
Remove this HTML comment when generating the user's actual curriculum.
-->

## Goal 1: <Concrete Practical Goal>

### Level 1: <Foundational Concept>

- **Core concept:** <Single clear mental model or mechanism that you can draw in ASCII.>
- **Source files:**
  - `./chapter-01.md` *(replace with exact relative path or verified official docs URL)*
- **Dependencies:** None
- **Done check:**
  - **In chat:** Explain how `<component A>` interacts with `<component B>` and solve one Socratic scenario without hints.
  - **Optional hands-on lab:** Run `<safe verification command or exercise>` and interpret the output.

---

### Level 2.1: <Dense Topic — Part 1>

- **Core concept:** <First half of a dense chapter, focused on one drawable flow or architecture.>
- **Source files:**
  - `./chapter-02.md` *(sections 2.1–2.3)*
- **Dependencies:** Level 1
- **Done check:**
  - **In chat:** Trace a request or data flow through the diagram step by step and identify one failure point.
  - **Optional hands-on lab:** Inspect `<config or state>` in your local environment and report what changes when `<parameter>` updates.

---

### Level 2.2: <Dense Topic — Part 2>

- **Core concept:** <Second half of a dense chapter, building directly on Level 2.1 and drawable in ASCII.>
- **Source files:**
  - `./chapter-02.md` *(sections 2.4–2.6)*
- **Dependencies:** Level 2.1
- **Done check:**
  - **In chat:** Design a solution to a constrained edge-case problem using the mechanism from this sub-level.
  - **Optional hands-on lab:** Apply `<configuration or code change>` and verify the expected behavior.

---

### Level 3: <Applied Integration>

- **Core concept:** <End-to-end flow combining Levels 1 through 2.2 into a working system diagram.>
- **Source files:**
  - `./chapter-03.md`
- **Dependencies:** Level 2.2
- **Done check:**
  - **In chat:** Walk through a realistic debugging or design task that integrates all Goal 1 concepts.
  - **Optional hands-on lab:** Build or verify `<Goal 1 milestone deliverable>` end to end.

---

## Optional (Skipped / Deferred)

Topics listed here are excluded from Goal 1. Promote any item to an active level whenever the learner asks.

### Skipped During Calibration

- **<Topic or Chapter Title>**
  - **Source files:** `./chapter-00.md`
  - **Reason:** Learner already demonstrated working knowledge during calibration.

### Deferred for Future Goals

- **<Chapter 04 Title>**
  - **Source files:** `./chapter-04.md`
  - **Reason:** Out of scope for Goal 1; available for Goal 2.

- **<Chapter 05 Title>**
  - **Source files:** `./chapter-05.md`
  - **Reason:** Out of scope for Goal 1; available for Goal 2.
