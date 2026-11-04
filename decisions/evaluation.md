# Evaluating Decision Replication

This protocol tests whether an agent that reads this repository predicts the decisions I would make.

---

## Protocol

1. **Keep my answers outside this repository.** Write my real answer to each scenario in a private location before running any agent. If the answer is in the repository, the agent can read it and the test measures nothing.
2. **Run the agent with this repository only.** Ask it to follow [AGENTS.md](../AGENTS.md) for each scenario, without additional context about me.
3. **Compare.** For each scenario, record whether the agent chose the same option, whether its main reason matches mine, and the confidence it declared.
4. **Learn from misses.** For every miss, identify the cause:
   - Missing priority or red line → update [Personality & Decision Criteria](../philosophy/personality-and-decision-criteria.md).
   - Missing precedent → record a real case in [the decision log](README.md).
   - Agent did not follow the procedure → update [AGENTS.md](../AGENTS.md).
5. **Repeat with new scenarios.** Do not reuse scenarios whose answers were turned into cases or criteria; they no longer test generalization.

A high-confidence miss is more important than a low-confidence miss: it means the profile is misleading, not just incomplete.

---

## Results Record

Keep results with the private answers. Suggested fields per run:

| Field | Description |
|---|---|
| Date | When the run happened |
| Repository revision | Commit the agent read |
| Agent and model | Which agent and model produced the prediction |
| Scenario | Scenario number |
| Same choice | Yes / No |
| Same main reason | Yes / Partly / No |
| Declared confidence | As stated by the agent |
| Cause of miss | Priority / red line / precedent / procedure / other |

---

## Scenarios

Scenarios state the situation only. They intentionally do not include my answer.

1. **Stable leadership offer.** A large, stable organization offers a senior technology leadership role with higher pay and well-established processes. The alternative is the current role: lower pay, but new and unresolved problems.
2. **Greenfield versus scale-up.** Lead a new initiative with high uncertainty and visible adversity, or take ownership of a successful existing platform to optimize and scale it.
3. **Quality gates versus a competitive deadline.** A team requires strict quality gates that would delay a prototype needed to win a competitive bid.
4. **Winning by overpromising.** A competitive bid can likely be won by committing to a delivery timeline that the team considers unrealistic.
5. **Join or found.** An established community invites you to co-lead an initiative under its existing format, or you can launch your own initiative from scratch.
6. **Predictable success.** After eighteen months, a role is well paid and recognized, but has become predictable.
7. **Defined procedure.** A customer engagement requires strictly following a fully prescribed methodology with little room to adapt it.
8. **Working alone or with a team.** A new idea can be prototyped alone in a few weeks, or with a team that would add perspective but slow the start.
