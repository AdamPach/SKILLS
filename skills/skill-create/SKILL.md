---
name: skill-create
description: "Create, continue, or revise a skill through scoped interviews and section-by-section drafting. Confirm shared understanding and obtain approval before saving."
disable-model-invocation: true
---

# Goal

Help the user create, continue, or revise a skill. Establish shared understanding of its overall process before drafting sections. Maintain agreed terminology and produce concise, explicit instructions, with supporting files when needed.

# Terminology

- **Process:** The actions and decisions through which a skill produces its intended outputs from its inputs.
- **Session:** A defined scope for establishing and confirming shared understanding.
- **Shared understanding:** The user-confirmed understanding reached within a session, including points they explicitly deferred or said they do not know.
- **Section proposal:** A summary of understanding, an explanation of intended behavior, and proposed section wording.
- **Approval to save:** Explicit authorization to save specific proposed content. Confirming shared understanding does not authorize saving.
- **Pending section:** A section blocked by an unresolved decision about required behavior.
- **Supporting file:** Templates, references, or other content used by the skill and kept outside `SKILL.md`.

# Inputs

- **Skill:** Required. A skill idea, desired outcome, or existing skill reference. Ask if missing.
- **Context:** Optional. Process ideas, constraints, examples, prior decisions, and supporting material.

A complete process is not required. Develop missing details through questions and options, with the user deciding.

Determine whether to create, continue, or revise the skill. For existing skills, read the skill and relevant prior decisions before asking questions. Follow clear handoffs without reconfirming settled decisions. Ask when the starting point is unclear.

Read supporting files only when needed to clarify the process or develop the current section.

# Outputs

- **Section proposals** for user review.
- **Skill file:** A new or updated `SKILL.md` containing content approved for saving.
- **Supporting files** needed by the skill, with instructions defining when and how to use them.

# Workflow

Use `interview` in Interview mode. Supply each session’s topic, perspective, scope, and available context, including prior answers and decisions. Follow its questioning and confirmation rules. Confirm shared understanding in each session before preparing its proposal. Apply Writing Rules throughout.

1. **Understand the overall process.**
   Start from the user’s idea and available context. Use an initial session to clarify the main actions, decisions, conditions, user involvement, and completion. For existing skills, reuse confirmed understanding and clarify the requested changes and their effects.

2. **Propose the structure and Goal.**
   For new skills, propose them together after confirming the overall process. Require Goal, Terminology, Inputs, Outputs, and Workflow; suggest other sections when useful. For existing skills, propose only necessary additions or revisions. Follow step 6 for approval and saving.

3. **Establish and maintain Terminology.**
   Develop initial definitions early in a dedicated session. Revisit them whenever discussion, drafting, or review introduces a term or changes its meaning. Check affected sections and supporting files for consistent usage. Follow step 6 for changes to approved definitions and wording.

4. **Develop one remaining section or supporting file at a time.**
   Give each its own session. Reuse earlier answers and revisit settled decisions only when new information affects them. Clarify missing behavior and contradictions before drafting. Follow Supporting Files when selecting the next file to develop.

5. **Handle unresolved decisions.**
   Keep deferred and unknown points explicit; session confirmation does not resolve them. When a decision prevents clear instructions, keep the affected section pending rather than inventing behavior. Resolve blocking conflicts before drafting dependent content. Continue independent work where possible; otherwise, explain which decisions are needed to continue.

6. **Propose, approve, and save.**
   Present the section proposal and ask whether to approve and save it. If the user requests changes or supplies replacement wording, revise the proposal and ask again. If intended behavior changes, revisit the affected session before proposing revised wording. Save only content explicitly approved for saving.

7. **Continue and review.**
   Continue with the next unfinished section or supporting file. Revisit pending sections when their blocking decisions are resolved. When drafting is complete, apply Final Review and address remaining issues through the same clarification and approval process.

# Writing Rules

Apply these rules to `skill-create`, every skill it produces, their supporting files, and their outputs:

- Use one agreed term for each concept. Define terms with specific or potentially ambiguous meanings in Terminology and use those definitions consistently.
- When wording or terminology is unclear, ask what the user means and which term to use.
- Replace vague wording with explicit instructions. Ask when doing so would require guessing.
- State when conditional instructions apply. Group related instructions under a clear shared condition.
- Use direct verbs and keep each instruction focused on one action or decision.
- Make required, optional, and prohibited behavior explicit.
- Remove repetition and filler while preserving necessary conditions, exceptions, and useful explanations.
- Define quality and completion requirements the agent can check.
- Consider supporting files for content needed only for specific tasks.

# Supporting Files

- Use supporting files for long content or material not needed on every run. When length motivates the recommendation, explain why and confirm placement during the interview.
- In the relevant `SKILL.md` section, link each file and explain its purpose, selection, and loading conditions. Load it only when those conditions apply.
- Develop a needed supporting file next. If blocked by an unresolved decision, keep it and dependent work pending while continuing independent work where possible.
- Follow Workflow for each file: its own session, confirmation of shared understanding, content proposal, and separate approval to save.
- Save only the skill and necessary supporting files. Do not create separate decision logs, progress files, or stored interview history.

# Final Review

Check the saved skill and its necessary supporting files:

- **Completeness:** Required and agreed sections are finished, with no unresolved placeholders or decisions blocking required behavior.
- **Process:** Instructions implement the confirmed actions, decisions, conditions, user involvement, and completion criteria.
- **Terminology:** Specific or potentially ambiguous terms are defined and used consistently across the skill, supporting files, and outputs.
- **Inputs and outputs:** Required inputs and missing-input handling are clear. Workflow explains how to produce each output.
- **Workflow:** The agent can determine what to do next, when to ask, and when to stop.
- **Consistency:** Instructions agree with each other and the confirmed intent.
- **Writing:** The skill and supporting files follow Writing Rules.
- **Supporting files:** Needed files exist, references resolve, and loading and usage instructions are clear.
- **Approval:** Saved content matches the user’s approval, with no requested changes outstanding.

Require every applicable check to pass. Explain any check marked not applicable; do not use a numerical score.

For failed or unverifiable checks, identify the remaining work and return to the affected section or file through Workflow. Recheck after approved changes are saved.

When every applicable check passes, explicitly state that the skill is ready.
