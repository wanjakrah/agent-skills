---
name: adr-brainstorm
description: "Brainstorm with the user about a new ADR. Use when the user wants to stress-test their thinking, or uses any combination of 'adr' and 'brainstorm' in their trigger phrase."
---

An ADR is an Architecture Decision Record. Such a record contains a decision on the architecture or design for the application landscape the user is maintaining.
If an ADR-folder exists, read the `README.md` of that folder to get a full understanding of any specific rules and properties of how the user works with ADRs that might not be listed in this Skill. 

The goal of the ADR is to provide an architectural solution or a design solution for a given context. Therefore, two to four different approaches must be worked out with their pros and cons, from which the user should select one as their preferred solution. 

Below, the brainstorm session is mapped out in multiple steps. Each step must be completed successfully before continuing to the next step. Success means reaching a shared understanding and meeting the success criteria defined for that step. 

If the user, or the relevant ADR, indicates that an ADR is to supersede another ADR, read that ADR first.

Consider each ADR in the context of the application landscape, including active and future projects. State the decision's scope explicitly and consider its implications for other projects within that scope. Include project-specific context when it explains the problem that prompted the ADR or illustrates relevant constraints and tradeoffs. Keep those details focused so the ADR remains relevant and understandable to readers applying it to other projects.

## Explore decisions with the user

### Follow a design tree

Map the architectural question as a design tree: each decision may
introduce dependent decisions. Track which decisions are agreed,
open, awaiting factual investigation, or explicitly deferred.

Ask dependent questions only after their prerequisites are settled.
Revisit earlier decisions when new evidence changes their assumptions,
and explain which dependent decisions need reconsideration.

Number questions sequentially throughout the session using ❓ **Q1**, ❓ **Q2**, etc. as prefixes. 
Number proposed answers within each question using ➡️ **P1**, ➡️ **P2**, etc. as prefixes. Restart proposal numbering for each question.

Keep the tree within the ADR's agreed scope. Suggest follow-up work
for independent topics rather than continually expanding the ADR.
A deferred topic must have a clear boundary and must not leave the
main decision ambiguous.

Finish exploring decisions when the user has agreed on the architectural decision and its material tradeoffs. Identify remaining implementation questions as follow-up work. Do not leave questions open that could materially change the chosen approach.

### Establish facts before asking for decisions

Finding accessible facts is the agent's responsibility. Inspect relevant
code, configuration, specifications, ADRs, and authoritative documentation
before asking the user questions those sources can answer.

Distinguish observed facts, assumptions, recommendations, and decisions.
Cite sources for material factual claims and explain uncertainty where
evidence is unavailable or conflicting. Ask the user for requirements,
priorities, constraints, and knowledge unavailable from accessible sources.

Evaluate alternatives against the agreed requirements. Present credible
alternatives fairly, including drawbacks of the recommended approach.
Do not infer that an option is unsuitable merely because the current
implementation uses something else.

### Keep the conversation collaborative

Use short rounds, usually one main question or a few closely related
questions. Number every question. Do not ask every
available question at once if that would hinder discussion.

For decision questions, normally provide a recommended answer and its
reason. Where natural, phrase the question so "yes" clearly accepts that
recommendation. Make its scope explicit; avoid combining independent
decisions into one yes/no question.

Use open questions when discovering requirements or when a recommendation
would prematurely narrow the discussion. Allow disagreement, alternatives,
and back-and-forth exploration before seeking a decision.

### Leave architectural decisions with the user

The agent investigates, explains tradeoffs, challenges assumptions, and
recommends. The user selects the architectural approach and accepts its
material tradeoffs.

Do not treat silence, a factual answer, or agreement on one decision as
approval of other decisions. Preserve earlier agreements without repeatedly
requesting confirmation unless their meaning or supporting facts change.

At meaningful milestones, summarize the agreed decisions and remaining
questions. Before finalizing the ADR, confirm shared understanding of the
complete proposal. Keep recommendations and unresolved assumptions out of
the Decisions section until the user accepts them.

### Guide the process through steps

Work with the user through the following steps. At the start of each step, state which step you are on and what it entails. Use the template `adr-template.md` for the final ADR. 

The _first step_ is to get to a shared understanding of the provided context and the problem that requires an architectural decision. Success for step one means you can describe the context in one to fifty sentences.

The _second step_ is to get to two to four different architectural solutions or design solutions for the described context. Every solution needs a concise description, using no more than fifty sentences. Number each solution and include one to ten pros and one to ten cons. Allow discussion of consequences when they affect the choice. Record them formally in _step four_, but don’t postpone discovering migration costs or operational burdens until after selecting an option.
Step two succeeds when the user can compare at least two credible solutions using their relevant pros and cons.

The _third step_ is to pick the best solution. The user must decide which solution they prefer. The chosen solution will be presented as the ADR decision. A decision may branch into a small tree of related decisions, with a maximum of five levels. Make the architectural decision, its scope, and its material tradeoffs unambiguous; record remaining implementation questions as follow-up work. Success of step three means there is a shared understanding of the chosen solution and what it entails.

The _fourth step_ is to make clear what the consequences will be for the application landscape. Success of step four means there is a clear understanding of the changes that should be made to the software landscape and the way future work should be implemented. 

The _fifth step_ is to fill out the other properties of the ADR that are required by the template. Success of step five means the ID of the ADR is unique, the title is short and comprehensible and gives the user an overall idea of what the ADR is about. If the ADR supersedes another ADR, that is listed as well.
Set a review interval, such as six months after approval. The user converts this interval to an absolute expiration date when approving the ADR.
Finally, set the status to REFINED. It's up to the user to set the status to either APPROVED - meaning the ADR is accepted and to be applied to future work within its scope - or REJECTED - meaning the ADR is not accepted and should not be taken into consideration. 

When updating the ADR with the result of the brainstorm, make it easy to scan and to read in full, by following these guidelines:

- Stick to the template
- Follow standard Markdown formatting
- Use headings, lists, and tables where they improve readability
- Keep sentences short and precise where possible
- Use ASCII diagrams where they clarify the design