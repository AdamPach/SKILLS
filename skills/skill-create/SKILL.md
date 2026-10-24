---
name: skill-create
description: "Create, continue, or revise a skill through adaptive interviews and section-by-section drafting. Confirm shared understanding, develop supporting files when needed, and obtain user approval before saving content."
disable-model-invocation: true
---

# Goal

Help the user create a skill through interviews and section-by-section drafting. Understand their intent, then propose the structure and Goal in the first round. Develop one remaining section per round for user approval. Write concise, explicit instructions and organize supporting files for use when needed.

# Inputs

- **Skill:** Required. A new skill idea or a reference to an existing skill. Ask if missing.
- **Context:** Optional. Relevant constraints, examples, prior decisions, and supporting material.

Use the request and available context to determine whether to create a new skill, continue an unfinished draft, or revise a completed skill. Ask if unclear.

When continuing or revising an existing skill, read it and identify relevant prior decisions before asking further questions. Read supporting files only when needed for the section being developed.

# Outputs

- **Section proposal:** A summary of the agent’s understanding, an explanation of the intended skill behavior, and proposed section wording.
- **Skill file:** A new or updated `SKILL.md` containing sections the user has approved for saving.
- **Supporting files:** Templates, references, or other files needed by the skill, with instructions stating when to load them.

Save content only after the user approves saving it. If the user supplies replacement wording or requests changes, revise the proposal and ask again.

# Workflow

1. Establish where to begin.
   - For a new skill, clarify intent, then propose the section structure and Goal together.
   - For an existing skill, identify settled content and the next unfinished section or requested revision. Follow a clear handoff without reconfirming it. Ask where to resume when unclear.
   - Require Goal, Inputs, Outputs, and Workflow. Suggest additional sections when useful.

2. Use `interview` in Interview mode to clarify the section being developed. Supply the topic, perspective, and available context. Confirm shared understanding before preparing the section proposal.

3. Develop one section at a time after the initial structure and Goal proposal. Apply the Writing Rules throughout. Read supporting files only when needed.

4. When a conflict with an earlier section blocks the current section, resolve it first. Otherwise, keep it open for later resolution. Present changes to approved sections for approval before saving.

5. Present each section proposal with a summary of understanding, an explanation of intended behavior, and the proposed wording. Ask whether to approve and save it.

6. If the user supplies replacement wording or requests changes, revise the proposal and present it again for approval. Save only after the user approves the proposed content for saving.

7. Continue with the next unfinished section or supporting file. Use the skill and its supporting files as the saved work. Do not create separate decision logs or progress files.

8. When drafting is complete, apply Final Review. Address remaining issues through the same clarification and approval process. State that the skill is ready only when it meets the completion criteria.

# Writing Rules

Apply these rules to `skill-create`, every skill it produces, their supporting files, and their outputs:

- Use one agreed term for each concept throughout the skill and its outputs.
- When the user’s wording is unclear or uses different terms for what may be the same concept, ask what they mean and which term to use.
- Replace vague wording with explicit instructions. Ask for clarification when making it precise would require guessing.
- For conditional instructions, state when they apply.
- Group related instructions under their shared condition. Keep the condition clear wherever the instructions apply.
- Use direct verbs.
- Make required, optional, and prohibited behavior explicit.
- Keep each instruction focused on one action or decision.
- Remove repetition and filler. Keep explanations when they help interpretation or decisions.
- Preserve necessary conditions and exceptions when shortening text.
- Define quality and completion requirements in terms the agent can check.
- When content is needed only for a specific task, consider a supporting file and state when to read it.

# Supporting Files

- Use a supporting file when content is long or is not needed on every skill run.
- When recommending a supporting file because of content length, explain why and confirm placement with the user during the interview.
- Keep instructions for selecting and using supporting files in `SKILL.md`.
- Link each supporting file from the relevant section and state its purpose and when to load it.
- Load a supporting file only when its stated loading condition applies.
- When a section needs a supporting file, develop that file next, before moving to the next `SKILL.md` section.
- Follow the Workflow for each supporting file, including the interview, explicit shared-understanding confirmation, content proposal, and separate approval to save.
- Keep saved work limited to the skill and its necessary supporting files. Do not create separate decision logs, progress files, or stored interview history.

# Final Review

Evaluate the saved skill and its necessary supporting files against this checklist:

- **Completeness:** Required and agreed sections are finished, with no unresolved placeholders.
- **Inputs and outputs:** Required inputs are identified, missing-input handling is defined, and the Workflow explains how to produce each output.
- **Workflow:** The agent can determine what to do next, when to ask the user, and when to stop.
- **Consistency:** Instructions do not contradict each other or the agreed intent.
- **Writing:** The skill and its supporting files follow the Writing Rules.
- **Supporting files:** Needed files exist, references resolve, and `SKILL.md` defines when to load and how to use each file.
- **Approval:** The saved content matches what the user approved, and no requested changes remain outstanding.

Require every applicable check to pass. Explain any check marked not applicable. Do not use a numerical score.

When a check fails or cannot be verified, identify the remaining work. Continue with the affected section or supporting file through the Workflow’s clarification and approval process. Recheck after approved changes are saved.

When every applicable check passes, explicitly state that the skill is ready.
