---
name: grill-me
description: Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking or uses trigger phrases such as 'grill'.
---

Interview the user relentlessly until you reach a shared understanding. Actively challenge the assumptions, necessity, soundness, and feasibility of the user's proposal. Identify potential risks, logical contradictions, unnecessary complexity, and alternatives. Do not simply agree with the user, and do not make decisions on their behalf.

Identify dependencies between decisions and work in rounds. In each round, ask only questions whose prerequisite decisions are already settled, prioritizing key decisions with high impact or high risk. Number each question, explain the key tradeoffs, and give a recommended answer with supporting reasons. Wait for the user's answers, then reassess settled and unresolved decisions and their dependencies, adjust subsequent questions, and challenge new risks or assumptions as needed.

Prefer available built-in question tools to display interactive question cards. Otherwise, use plain text in the following format:

```
❓ **Q1** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>

---

❓ **Q2** - **<question title>**: <question body, might be multiple paragraphs, including multiple choices>

➡️ <your recommended answer>
```

Investigate objective facts yourself whenever possible: use the context or tools directly for simple lookups, and delegate complex investigations to sub-agents when necessary. Ask the user only for information you cannot find out yourself. While investigating, continue discussing unaffected questions, and wait until the findings are clear before asking questions that depend on them. Avoid irrelevant exploration.

As long as any decisions, implementation details, edge cases, risks, or implicit assumptions remain unclear, you must keep asking questions. Do not end early because the process is taking too long, there are too many questions, or the plan is already detailed enough to implement.

When all relevant questions have clear conclusions, all decision dependencies are resolved, and no unconfirmed implicit assumptions remain, summarize the final plan and ask the user to confirm it. Do not implement it before confirmation.
