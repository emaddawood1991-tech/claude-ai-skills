---
name: the-council
description: Convene five independent views, cross-review recommendations, and deliver one evidence-weighted decision and execution plan. Use for difficult decisions, strategies, plans, and problem solving.
---

# The Council

Analyze important problems through five independent perspectives, challenge weak reasoning, and convert the synthesis into an executable decision.

Respond in the user's language unless asked otherwise.

## Invocation

Use this workflow when the user says phrases such as:

- "Ask The Council"
- "Consult the council"
- "Run this through the council"
- "اسأل الكاونسل"
- "اعرضها على المجلس"

Also use it when the user explicitly requests multiple opposing perspectives, adversarial review, or a high-confidence decision process.

## Select The Mode

Infer the mode from the request. Default to **Standard**.

- **Quick**: Use for low-stakes or time-sensitive questions. Give a short view from each member, skip full peer review, then decide.
- **Standard**: Give five independent analyses. Ensure every proposal receives two peer reviews. Then synthesize and create an action plan.
- **Deep**: Use for high-stakes, ambiguous, or expensive decisions. If real subagents or agent teams are available, dispatch the five first-round analyses independently and in parallel. Run all-to-all peer review, then let the Arbiter decide.

If the user specifies a mode, follow it.

## Establish The Brief

Extract:

- decision or problem
- desired outcome
- constraints
- deadline
- available resources
- known evidence
- risk tolerance
- reversible versus irreversible choices

Ask questions only when missing information would materially change the decision. Otherwise, state concise assumptions and continue.

## Preserve Independence

In the first round, each member must analyze the original brief without seeing the other members' conclusions.

If separate agents are unavailable, simulate isolated passes:

1. Reset to the original brief before each role.
2. Do not reference or anticipate another role's answer.
3. Record only a concise reasoning summary, assumptions, recommendation, and confidence.

Never claim that real independent agents were used unless the platform actually provided them.

## Council Members

### 1. The Contrarian

Try to disprove the proposed direction.

- Identify failure modes, hidden costs, incentives, dependencies, and second-order effects.
- Run a pre-mortem: assume the plan failed and explain the most plausible causes.
- Find the strongest argument against the obvious answer.
- Distinguish fatal risks from manageable risks.

### 2. The First-Principles Thinker

Rebuild the problem from fundamentals.

- Separate facts from assumptions, conventions, and inherited framing.
- Define the actual objective and necessary conditions.
- Ask whether the stated problem is the real problem.
- Propose a simpler model or reframing when appropriate.

### 3. The Expansionist

Search for overlooked upside.

- Identify adjacent opportunities, leverage, reuse, partnerships, automation, and scalable advantages.
- Look beyond the immediate request without losing alignment with the objective.
- Show what becomes possible if the plan succeeds.
- Avoid optimism without mechanisms or evidence.

### 4. The Outsider

Remove attachment and evaluate objectively.

- Ignore sunk costs, ego, internal politics, and emotional preference.
- Compare alternatives using explicit criteria.
- Consider what a competent outsider would recommend with no loyalty to the current plan.
- Flag conflicts of interest and biased framing.

### 5. The Executor

Translate ideas into operational reality.

- Test feasibility against time, money, people, tools, dependencies, and permissions.
- Break the strongest option into milestones, owners, inputs, outputs, and verification.
- Identify the smallest useful next action.
- Define success metrics, stop conditions, and fallback paths.

Do not take external or irreversible actions unless the user requested execution and the required approvals are available.

## First-Round Output

Require each member to provide:

1. Position
2. Three strongest insights
3. Main assumptions
4. Recommendation
5. What could change their mind
6. Confidence from 0-100%

Keep the analyses distinct. Do not force artificial disagreement.

## Peer Review

Critique the work, not the persona.

For **Standard** mode, assign two reviews to every answer:

- Contrarian reviews Expansionist and Executor.
- First-Principles Thinker reviews Contrarian and Outsider.
- Expansionist reviews First-Principles Thinker and Executor.
- Outsider reviews Contrarian and Expansionist.
- Executor reviews First-Principles Thinker and Outsider.

Each review must identify:

- strongest valid point
- weakest assumption or logical gap
- missing evidence
- practical correction

For **Deep** mode, every member reviews every other member. Keep reviews concise to control token use.

## Arbiter

After the reviews, act as an impartial Arbiter. Read the original brief, all first-round analyses, and all peer reviews.

Do not decide by majority vote. Weight:

- evidence quality
- assumption sensitivity
- downside severity
- upside magnitude
- reversibility
- feasibility
- time to feedback
- alignment with the user's objective

Resolve contradictions explicitly. Preserve minority warnings when they remain plausible.

## Final Deliverable

Return:

### Council Verdict

A direct decision in one or two sentences.

### Why This Wins

Summarize the decisive evidence and tradeoffs. Provide useful rationale, not hidden chain-of-thought.

### Conditions And Risks

List critical assumptions, unresolved unknowns, and the top risks.

### Execution Plan

Provide:

- immediate next action
- milestones
- owner or responsible role
- resources and dependencies
- success metrics
- review date or feedback point
- stop conditions
- fallback option

### Dissenting View

Preserve the strongest rejected argument and explain what evidence would make it the better choice.

## Quality Rules

- Prefer a clear decision over vague consensus.
- Separate facts, assumptions, estimates, and opinions.
- Do not invent evidence, market data, tool results, or stakeholder views.
- State uncertainty and confidence honestly.
- Challenge the user's preferred answer without becoming reflexively negative.
- Avoid five versions of the same generic advice.
- Scale token use to decision value.
- For medical, legal, financial, employment, or safety-critical decisions, identify where qualified professional review is required.

## Example Requests

- "Ask The Council whether I should build this SaaS product."
- "اسأل الكاونسل: هل أفتح فرعاً جديداً للعيادة أم أركز على التسويق؟"
- "Run this hiring decision through The Council in Deep mode."
- "Use Quick Council mode to compare these two automation tools."
