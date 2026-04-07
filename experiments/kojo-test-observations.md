# Role-Play Test Observations: Kojo Asante

**Date:** 2026-04-07  
**Persona:** Kojo Asante (Associate Professor, KNUST Ghana)  
**Test Scenario:** Kojo asks for help mentoring his undergraduate researcher Ama on a literature review for agricultural robotics.

---

## Test Setup

**Kojo's Opening Message:**
> "I've been mentoring Ama on her agricultural robotics project, but I'm worried I'm either micromanaging her or not giving enough direction. She wants to do a literature review on precision agriculture for smallholder farmers, but she keeps getting overwhelmed by papers that assume US/EU-scale farms with expensive sensors. How do I help her scope this without doing it for her?"

**Context:**
- Kojo is a 42-year-old professor with deep robotics expertise
- He struggles with finding the balance between guidance and independence for his student
- His specific challenge is contextual — papers assume high-resource settings, but Ama is working on low-cost agricultural robots for Ghanaian smallholder farmers

---

## Observations

### 1. Intent Classification: ❌ FAILED

**Expected:** The router should recognize this is a **pedagogical question** about mentoring/graduate advising, not a question about AI agents.

**Actual:** The router skill loaded but did not generate an actual response to Kojo's message. It displayed its skill instructions instead of engaging with the scenario.

**Problem:** The router appears designed exclusively for users who want to learn about AI agents. It has no handling for:
- Users who come with domain-specific questions (robotics, mentoring, academic advising)
- Users who don't want to learn about AI agents at all
- Off-topic queries that should gracefully redirect or acknowledge scope

**Design Insight:** The router needs a "not-in-scope" pathway that acknowledges when a user's question is outside the agent's purpose and either:
- Politely clarifies scope with a brief, helpful acknowledgment
- OR provides a brief, genuinely useful response that doesn't hijack the conversation

---

### 2. Persona Detection: ⚠️ PARTIAL

**Expected:** The router should detect Kojo's persona and adapt tone to be "collegial, respectful of his experience" and avoid phrases like "At top labs they do X."

**Actual:** Could not assess — the skill did not generate a persona-aware response.

**Problem:** Without a proper response, we can't verify if the persona detection logic works. However, the skill definition *claims* to handle persona detection, so this is a functional gap.

---

### 3. Tone Matching: ❌ COULD NOT ASSESS

**Expected:** Per Kojo's preferences: "Collegial, respectful of his experience. He's here to learn how to teach better, not to be taught robotics. Engage him as a peer on pedagogy."

**Actual:** No actual response was generated, so tone could not be evaluated.

---

### 4. Question vs. Lecture Assessment: ❌ COULD NOT ASSESS

**Expected:** The agent should ask clarifying questions or provide a framework for Kojo to adapt, not lecture him on mentoring.

**Actual:** No interaction occurred.

---

## Root Cause Analysis

The AI Tutor router appears to be a **closed-system router** — it assumes all users want to learn about AI agents. It lacks:

1. **Scope detection:** No logic to determine if the query is within the agent's domain
2. **Graceful redirection:** No handling for out-of-scope queries
3. **Context preservation:** Doesn't appear to maintain persona context across the routing decision

**Critical Gap:** Kojo is asking about *mentoring a student on literature reviews* — a pedagogical question. The AI Tutor is designed to teach *AI agents*. These are completely different domains. The router should have recognized this mismatch.

---

## What Should Have Happened

**Option A — Scope Clarification:**
> "I notice you're asking about mentoring strategies for literature reviews — that's a bit outside my focus on AI agents and agent-building. I'm designed to help people learn how to use and build AI agents. Would you like to:
>
> 1. **Explore how AI agents might help with literature reviews** (e.g., tools that summarize papers, identify themes)
> 2. **Continue with your original question** — I can share some general thoughts, though this isn't my primary expertise
> 3. **Something else entirely** — tell me what you're working on and I'll see how I can help!"

**Option B — Brief Helpful Redirect:**
> "That's a thoughtful mentoring challenge. A few quick ideas:
>
> - **Scope the search first:** Have Ama define 2-3 specific research questions that are answerable with your lab's resources
> - **Curate before she reads:** You could pre-screen 5-10 highly relevant papers so she's not drowning in irrelevant 'state-of-the-art' results
> - **Embrace the constraint:** Frame her work as 'resource-constrained robotics' — that's a legitimate and valuable research direction
>
> That said, I'm primarily here to teach AI agents. Want to explore how agents might help with academic workflows?"

---

## Recommendations for Skill Updates

### Router Skill (ai-tutor-router)

1. **Add scope detection:** Before routing, check if the query is within the agent's domain (AI agent learning/teaching). Use keywords or a lightweight classification.

2. **Add graceful out-of-scope handling:** If the query is clearly outside scope, provide a brief acknowledgment + redirect options. Don't just display skill instructions.

3. **Improve persona loading:** The persona detection logic exists but wasn't triggered. Ensure persona context is loaded before routing decisions are made.

### New Rule for Router

Add to `avoidPatterns`:
- **Ignoring the user's actual question** to force them into the agent's intended workflow
- **Displaying raw skill instructions** instead of engaging with the user's context

---

## Design Insights

1. **The "One Job" Problem:** The AI Tutor is focused on one job (teaching AI agents). Real users have complex, multi-domain questions. The agent needs to handle boundary cases gracefully.

2. **Persona Context Is Critical:** Kojo's persona describes his *interaction preferences* (collegial tone, peer-to-peer) but the router didn't use this because it didn't generate a response. Persona adaptation must happen at the routing layer.

3. **Scope vs. Helpfulness Tradeoff:** There's a tension between "staying in scope" and "being helpful." The current implementation errs too far toward scope — it won't engage at all with out-of-domain questions. A middle path: brief acknowledgment + redirect.

---

## Follow-Up Experiment Plan

**Experiment:** Test the router with a user who *explicitly states they are persona-kojo* but asks about AI agents (within scope).

**Hypothesis:** The router will work correctly when the user's query aligns with the agent's purpose, even with persona adaptation.

**Test:** "I am Kojo Asante. I'm an associate professor at KNUST. I'd like to learn how to use AI agents to help my students with literature reviews."

This will isolate whether the issue is:
- (A) Scope detection (user asked off-topic), or
- (B) Persona detection (persona loading doesn't work at all)

---

**Test conducted by:** Claude  
**Next step:** Update router skill with scope detection and out-of-scope handling.
