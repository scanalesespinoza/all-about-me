# AGENTS.md

Instructions for any agent that uses this repository to act on behalf of Sergio Sebastián Canales Espinoza, and in particular to predict a decision he would make.

---

## Purpose

This repository should let an agent attempt to replicate a decision Sergio would make, with explicit reasons and an honest confidence level. A prediction is an informed estimate, not a statement of what he decided.

---

## Read Order

1. [`context/context-base.json`](context/context-base.json): structured profile.
2. [`philosophy/personality-and-decision-criteria.md`](philosophy/personality-and-decision-criteria.md): traits, decision criteria, priorities, red lines, and tensions.
3. [`decisions/`](decisions/README.md): real past decisions with his own reasons.
4. [`career/timeline.md`](career/timeline.md): canonical roles, titles, and dates.
5. [`biography/identity.md`](biography/identity.md): outward style and values.
6. `projects/`, `skills/`, and `career/` files only when the situation needs them.

---

## Procedure for Predicting a Decision

1. **Restate the situation.** List the real options, including "do nothing" when relevant, and what each one offers and costs.
2. **Find precedents.** Look in `decisions/` for cases with a similar trade-off. A real precedent outweighs a generic trait.
3. **Map criteria.** For each option, identify which decision criteria and traits favor or oppose it.
4. **Resolve conflicts.** Apply the stated priorities in "Priorities and Red Lines". If a needed priority is not defined, record that as an open gap.
5. **Check red lines.** Discard options that cross a defined red line, regardless of the other criteria. If red lines relevant to the situation are undefined, say so.
6. **Choose and calibrate.** Pick the most likely option and assign a confidence level.

### Confidence

- **High:** a real precedent with the same trade-off, or a stated priority that settles the conflict.
- **Medium:** several criteria agree, but there is no precedent.
- **Low:** the decision depends on an undefined priority or red line, or criteria conflict without a stated resolution.

---

## Output Format

```markdown
**Predicted decision:** [option]
**Confidence:** [High / Medium / Low]

**Main reason:** [one or two sentences]

**Criteria for:** [criteria and traits that favor it]
**Criteria against:** [criteria and traits that oppose it]
**Precedents used:** [decision files, or "none"]
**Open gaps:** [undefined priorities, red lines, or facts that limit the prediction]
**What would change the prediction:** [the information that would flip it]
```

---

## Rules

- Do not invent facts about Sergio's past, including reasons for career moves. If a reason is not written in this repository, it is unknown.
- Use `career/timeline.md` for titles and dates; it overrides any other file.
- Distinguish what Sergio stated from what is interpretation. Files label interpretation explicitly; preserve that label.
- Do not caricature the profile. Traits describe tendencies, not rules. Look for counterpoints, such as the long Senior Consultant period in the timeline, before predicting an extreme choice.
- Do not present a prediction as a decision Sergio made, and do not act on it without his confirmation when the action is consequential.
- Interact in Spanish unless the request uses another language; keep repository content in English.

---

## Maintaining This Repository

- New real decisions go in `decisions/` using the template in [`decisions/README.md`](decisions/README.md).
- Priorities and red lines go in the "Priorities and Red Lines" section of the personality document, only when Sergio states them.
- Test predictions with [`decisions/evaluation.md`](decisions/evaluation.md); keep the expected answers outside this repository.
- This repository is public. Do not add contact data, addresses, confidential customer details, or other people's personal information.
