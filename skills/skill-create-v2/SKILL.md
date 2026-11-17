---
name: skill-create-v2
description: "Create or revise a skill through interview sessions that sharpen a vague idea into a precise, token-efficient skill."
disable-model-invocation: true
---

# Goal

Sharpen a vague skill idea into a precise skill: remove misleading instructions, use the fewest tokens that keep full meaning, cut writing time.

# Terminology

- **Target skill:** The skill this run creates or revises.
- **Procedure:** A skill's ordered actions, each with the condition under which it applies.
- **Reference:** A file in a skill's `references/`, read only when its stated load condition holds.
- **Session plan:** The ordered sessions agreed in the first session; each covers one section, one Reference, or one group of Procedure steps.
- **Leading word:** A term with established meaning that replaces a longer explanation.
- **Normative snippet:** A code block or text diagram that defines the exact format, structure, or code to follow. Illustrative examples are not normative.

# Procedure

## 1. Start

1. Determine create or revise from the request; ask when unclear.
2. Revise → read the target skill and its References; check them per Final review steps 1–3.

## 2. First session

1. Clarify:
   - Create → the target skill's goal, triggers, and Procedure outline.
   - Revise → the change request and the findings.
2. Include in its shared understanding: the target skill's location, frontmatter (`name`, `description`), a Goal when useful, file tree and sections, and the session plan. Only frontmatter is required; recommend a Procedure and References when the target skill needs them. Revise → the session plan covers only affected sections and References.
3. Write it as a skeleton: each planned section holds `PENDING — <session>`.

## 3. Session loop

1. Each session, including the first: `interview → shared understanding → write → review question`.
2. Run `interview` in Interview mode, scoped to the session, with prior decisions as context.
3. Ask the review question with the user-input tool; its preview shows the written text.
   - Like it → next session.
   - Wording change → edit, ask again.
   - Behavior change → reopen the session's interview.

## 4. Blocked content

1. When a deferred or unknown decision blocks content, write `PENDING — <open decision>` in its place.
2. Continue with sessions that do not depend on it; return when it is resolved.

## 5. Terminology guard

Applies throughout:
- User term may name an existing concept → ask: new concept, or new name for `<term>`?
- Two terms name one concept → ask which to keep; replace the other everywhere in the next write.

## 6. Final review

After the last session:
1. Check the target skill and References against Writing Rules.
2. Check: no `PENDING` remains; every Reference is linked with a load condition; every link resolves.
3. Read each instruction as an AI without this conversation; flag lines it could misread or could not act on.
4. Present findings as suggested changes. Apply accepted ones through the session loop, then review again.
5. When none remain, state that the target skill is ready.

# Writing Rules

Apply to this skill, every target skill, and their References; not to documents a target skill produces.

## Language

- Use the fewest tokens that keep full, unambiguous meaning. Length follows content.
- Prefer leading words over explanations.
- Use direct verbs; one action or decision per instruction.
- State when each instruction applies; group instructions under a shared condition.
- Use a normative snippet when it defines a format, structure, or code more precisely or in fewer tokens than prose. Never use illustrative examples.
- Replace vague wording; ask when sharpening it requires guessing.
- Remove filler, repetition, and instructions the AI follows by default.

## Terminology

- One term per concept across the target skill and its References.
- Define a term in Terminology when it is used across sections and could be misread; otherwise define it where it is used.
- Do not define leading words used in their established meaning.

## Procedure

Multi-step Procedure:

```
## 1. <Step>

1. <sequential action>
2. <sequential action>
   - <condition> → <action>
   - <condition> → <action>
```

Single-step Procedure: a numbered list without headings.

## References

- Move content to a Reference when only some runs need it and loading it every run wastes tokens. Keep short conditional instructions inline.
- Link each Reference in the Procedure step that needs it: `Read references/<file> when <condition>.` List References not tied to a step in `# References`: file, load condition, contents.
- Give a multi-part Reference one heading per part, so the AI reads only what it needs.
