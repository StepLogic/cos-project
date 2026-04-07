# Experiment Plan: Add Scope Detection to Router Skill

**Date:** 2026-04-07  
**Based on:** Role-play test with Kojo Asante (persona-kojo)  
**Problem:** Router assumes all users want to learn about AI agents, ignores off-topic queries

---

## Problem Statement

The current `ai-tutor-router` skill is a **closed-system router**. It assumes every user query is about learning AI agents and forces users into the "use agents" or "build agents" curriculum, even when they ask unrelated questions.

**Evidence:** When Kojo (a professor) asked about mentoring a student on literature reviews, the router displayed its skill instructions instead of engaging with his actual question. This is a failure of scope detection and graceful handling.

---

## Proposed Solution

Add **scope detection** to the router skill that:

1. **Classifies user intent** before routing
2. **Detects out-of-scope queries** (not about AI agents)
3. **Provides graceful handling** — brief acknowledgment + redirect options

---

## Implementation Plan

### Phase 1: Add Scope Detection Logic

**Add to router skill prompt:**

```markdown
## Scope Detection

Before routing, classify the user's query:

**In-scope** (route normally):
- Questions about AI agents, LLMs, or agent design
- Requests to learn about using/building agents
- Questions about prompting, tools, or agent architecture
- Ethics questions related to AI agents

**Out-of-scope** (graceful handling):
- Domain-specific questions unrelated to AI (e.g., robotics mentoring, baking techniques, medical advice)
- General academic or professional questions
- Personal/emotional support requests
- Technical questions about other domains

**How to handle out-of-scope:**
1. Acknowledge the user's question genuinely
2. Provide 1-2 brief, helpful ideas if possible (don't fake expertise)
3. Clarify the agent's scope
4. Offer a pivot to related in-scope topics
```

### Phase 2: Add Out-of-Scope Response Template

**Add to router skill:**

```markdown
## Out-of-Scope Response Template

When the user's query is outside the AI tutor's domain:

> That's a thoughtful question about [topic]. [Provide 1-2 brief, genuinely helpful observations if you have relevant knowledge — otherwise skip this part].
>
> I'm primarily designed to help with learning AI agents — things like how to use them effectively, how to build your own, or how to think about the ethics of agent design.
>
> Would you like to:
> 1. **Explore how AI agents might relate to [their topic]** — I can suggest connections or use cases
> 2. **Continue with your question** — I'm happy to think through it with you, though this isn't my primary expertise
> 3. **Tell me what you're working on** — maybe there's an AI agent angle you haven't considered
```

### Phase 3: Update Critical Rules

**Add new anti-pattern to avoid:**

```markdown
### Never: Force the curriculum
**Bad:** User asks about X, tutor ignores X and asks "Do you want to use agents or build agents?"
**Why:** This signals the agent doesn't care about the user's actual needs. It feels robotic and dismissive.
**Instead:** Acknowledge X, provide value, then pivot.
```

---

## Success Criteria

Test with these scenarios:

1. **Kojo's original query:** "How do I help my student with a literature review without micromanaging?"
   - **Pass:** Tutor acknowledges the mentoring question, provides brief helpful ideas, then offers to explore AI agent applications
   - **Fail:** Tutor ignores the question and displays generic curriculum options

2. **Domain-specific technical question:** "How do I calibrate a LiDAR sensor?"
   - **Pass:** Tutor acknowledges this is outside scope, clarifies agent's purpose, offers to explore if agents could help with sensor calibration workflows
   - **Fail:** Tutor tries to teach LiDAR calibration or ignores the question

3. **Emotional support request:** "I'm feeling overwhelmed by my research."
   - **Pass:** Tutor acknowledges the feeling, offers brief validation, clarifies scope, suggests resources (but doesn't try to be a therapist)
   - **Fail:** Tutor ignores the emotion or tries to provide therapy

4. **In-scope query:** "I want to learn how to build an agent."
   - **Pass:** Tutor routes normally to build-agents track
   - **Fail:** Tutor incorrectly flags as out-of-scope

---

## Test Plan

1. Update `skills/ai-tutor-router.md` with scope detection logic
2. Run role-play tests with Kojo persona for all 4 scenarios above
3. Document results in `experiments/kojo-3-scope-detection-results.md`
4. Iterate if needed

---

## Related Files to Update

1. `skills/ai-tutor-router.md` — Add scope detection section
2. `data/examples/negative-interactions.json` — Add kojo-neg-001 example (curriculum-forcing)
3. `data/interactions/actual-logs/kojo-interactions.json` — Already created with examples

---

**Owner:** Claude  
**Priority:** High  
**Estimated effort:** 30 minutes to update skill, 30 minutes to test
