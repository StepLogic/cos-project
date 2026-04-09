# **Sage**: An AI Tutor for Learning to Use AI Agents
*COS 598/498: Generative AI Agents · Spring 2026 · University of Maine · Group 10*

---

## **1. The Problem**

### Step 1 — State the Problem

Students and professionals are increasingly expected to work with AI agents, yet most learning resources fall into two extremes: passive video lectures that explain concepts without practice, or raw documentation that assumes prior expertise. Learners need to develop practical judgment—knowing when to trust an agent, how to verify its work, when to intervene—but current approaches don't scaffold the development of this judgment through guided, interactive practice. This gap leaves learners either hesitant to use AI (missing opportunities) or overconfident (taking risks they don't understand).

### Step 2 — Concrete Example

**Maya Chen**, a second-year undergraduate in Computer Science, has heard that Claude Code can help with debugging but doesn't know where to start. She watches a YouTube tutorial that demonstrates a flashy demo, but when she tries herself, she's unsure: Should she accept the agent's suggested fix? How does she know it won't break something else? She asks Claude "fix my code" and gets a generic response. Frustrated, she either gives up on using agents or accepts changes blindly without understanding them. Maya needs a learning companion that meets her where she is, guides her through interactive practice, and helps her develop judgment—not just technical skills.

### Step 3 — Prior Solutions

1. **Video-based courses** (Udemy, Coursera) provide structured content but are passive; learners watch someone else use AI without doing it themselves.
2. **Documentation and tutorials** (Claude Code docs, LangChain guides) are comprehensive but assume self-directed learning; they don't adapt to the learner's level or provide feedback on their attempts.

### Step 4 — Gap in Prior Solutions

Prior solutions don't address these multiple causes together:

- **Passive consumption vs. active learning:** Watching videos doesn't build practical judgment; learners need to do, reflect, and iterate.
- **Generic content vs. adaptive guidance:** Documentation is one-size-fits-all; learners need scaffolding that adjusts to their level and context.
- **Skills without ethics:** Most resources teach *how* to use agents but not *when* or *whether* to use them, leaving learners without frameworks for responsible use.
- **Isolation vs. community:** Learning to use AI is often solitary; learners benefit from seeing others' interactions and reflecting together.

### Step 5 — Design Question

**How might an AI agent, with access to learning context, prior AI interactions, and collaborative channels, provide interactive, adaptive tutoring that teaches learners to use AI agents effectively, verify their work, and develop ethical judgment?**

---

## **2. Why Bother**

### Scale and Impact

AI agents are rapidly becoming standard tools in software development, data science, writing, and research. Yet surveys indicate that while 70% of students have tried AI tools, only 15% feel confident using them effectively. The gap between exposure and mastery represents a significant barrier to workforce readiness and academic success. When learners don't develop judgment—knowing when to trust, how to verify, when to intervene—they either underutilize powerful tools or take unchecked risks.

### Equity Dimension

This problem disproportionately affects learners without prior technical mentorship. Students from under-resourced institutions, first-generation college students, and those without professional networks lack the informal guidance that helps others develop AI judgment. A structured, accessible tutor could democratize access to AI literacy that is currently learned through privilege and proximity to experts.

### Timeliness

Now is the right moment because:

1. **The CollaborAITE platform** provides unique affordances: visible AI interactions in channels, shared learning contexts, access to class materials, and learner reflection data.
2. **AI agents are mature enough** to be useful but new enough that most learners haven't yet developed expertise—there's a window to shape good practices.
3. **The pedagogical need is urgent:** As AI becomes embedded in education, learners need critical AI literacy to use these tools responsibly and effectively.

---

## **3. Status Quo**

### Prior Solution Category 1: Video-Based Courses (Udemy, Coursera, YouTube)

**Solution Overview**

Platforms like Udemy's "Agentic AI Mastery" and Coursera's prompt engineering courses offer structured video content with coding demonstrations. Learners watch instructors use AI agents and complete exercises afterward.

**How Learners Use It**

1. Watch video lecture (30-60 minutes)
2. Follow along with provided code/exercises
3. Complete quiz or project for certificate
4. Return to videos for reference

**Where It Falls Short**

- **Passive learning:** Watching someone else succeed doesn't build learner judgment
- **No real-time feedback:** Can't ask "why did that work?" or "what if I tried this?"
- **Generic scenarios:** Exercises don't match the learner's actual context or challenges
- **Ethics as add-on:** Responsible AI covered in separate modules, not integrated into practice

**How Sage Differs**

Sage provides interactive, Socratic practice where learners make decisions and receive immediate feedback, not watch demonstrations. It adapts to the learner's actual context (course materials, prior attempts) and weaves ethical considerations into every exercise.

---

### Prior Solution Category 2: Documentation and Tutorials (Claude Code Docs, LangChain Academy)

**Solution Overview**

Official documentation provides comprehensive reference material. LangChain Academy offers free, self-paced modules with hands-on coding.

**How Learners Use It**

1. Navigate to docs when stuck
2. Follow getting-started guides
3. Copy-paste code examples
4. Iterate through trial and error

**Where It Falls Short**

- **Steep learning curve:** Assumes self-directed learners who know what they don't know
- **No scaffolding:** Beginners don't know which concepts to learn first or how they connect
- **Isolation:** No visibility into others' struggles or strategies
- **Reference, not teaching:** Optimized for lookup, not for building understanding progressively

**How Sage Differs**

Sage acts as a warm, encouraging tutor that meets learners where they are, asks diagnostic questions to assess level, and guides them through structured learning paths. It leverages CollaborAITE's channel data to show relevant examples from peers and facilitate reflection.

---

### Prior Solution Category 3: Existing AI Agents (ChatGPT, Claude Web Interface)

**Solution Overview**

General-purpose AI assistants that learners might try to use for learning, but which are optimized for task completion, not pedagogy.

**How Learners Use It**

1. Ask "how do I use AI agents?"
2. Receive generic explanation
3. Try follow-up questions
4. May get frustrated by lack of structure or progression

**Where It Falls Short**

- **Task-focused, not learning-focused:** Optimized to answer, not to teach
- **No learning progression:** Doesn't scaffold from beginner to advanced
- **No reflection:** Doesn't prompt learners to think about what they learned
- **No contextual awareness:** Can't see the learner's course materials, prior struggles, or progress

**How Sage Differs**

Sage is explicitly designed as a tutor, not an assistant. It asks questions to diagnose level, provides structured tracks (Using vs. Building), includes guided reflection after practice, and leverages CollaborAITE's contextual data to personalize learning.

---

## **4. Your Proposed Agent**

| **Agent Name** | **Sage** |
| :---- | :---- |
| **Description** | A warm, interactive AI tutor that teaches you to use and build AI agents through practice, reflection, and ethical thinking |
| **Team Name** | Group 10 |
| **Team Members** | [Names TBD] |

---

### **4a. Agent Summary**

**Sage** is an AI tutor that lives on CollaborAITE and teaches learners how to work with AI agents effectively. It combines interactive practice exercises, Socratic questioning, guided reflection, and ethical consideration into a personalized learning experience. Sage operates through a core interaction loop: diagnose level → provide exercise → learner attempts → feedback and coaching → guided reflection → progress to next challenge.

**How Sage Addresses Root Causes:**

**Passive vs. Active Learning:** Sage provides hands-on simulated environments where learners make real decisions about agent use—when to prompt, how to review output, when to intervene. For example, a "Spot the Problem" exercise shows agent output and asks the learner to identify issues before accepting. Immediate feedback reinforces learning through doing.

**Generic vs. Adaptive:** Sage uses CollaborAITE's data (course materials, prior AI interactions, user reflections) to personalize content. If a learner is in a data science course, Sage uses relevant examples. If they've struggled with verification in past interactions, Sage provides additional scaffolding on reviewing agent work.

**Skills Without Ethics:** Every exercise in Sage includes an ethical dimension. The "Agent or No Agent?" classification exercise asks learners to identify when AI is appropriate versus when simpler tools suffice. The "Improve This Prompt" exercise includes "What could go wrong?" reflection. Ethics is woven throughout, not siloed.

**Isolation vs. Community:** Sage can surface anonymized examples from channel conversations (with permission) to show how peers approached similar challenges. Reflection prompts encourage learners to share insights with their group, turning individual learning into collective knowledge-building.

---

### **4b. Data Sources**

| **CollaborAITE Data Source** | **How Sage Uses It** |
| :---- | :---- |
| **Class slides and activities** | Sage references current course content to provide contextually relevant examples and ensure alignment with learning objectives. |
| **Channel conversations (AI queries)** | Sage analyzes patterns in learner AI interactions to identify common struggles and personalize scaffolding. Can surface anonymized peer examples for reflection. |
| **User profile information** | Sage uses stated experience level, learning goals, and preferences to select appropriate tracks (Using vs. Building) and difficulty levels. |
| **User-uploaded documents** | Learners can share assignments or projects; Sage uses these to create relevant practice scenarios (e.g., "improve this prompt for your actual assignment"). |
| **Prior assignments and reflections** | Sage reviews reflection patterns to identify growth areas and celebrate progress. Informs personalization of future exercises. |
| **Anonymized session transcripts** | Sage uses class-level patterns to identify topics where many learners struggle, prioritizing those in recommendations. |

**Privacy-by-Design:**

- **What Sage does NOT access:** Individual grades or assessment scores (not relevant to tutoring, could create bias).
- **What Sage does NOT access:** Private direct messages between learners (only public channel content with permission).
- **What Sage does NOT access:** Learner data from outside CollaborAITE (respects platform boundaries).

---

### **4c. Other Data Sources**

**External Data Source: AI Agent Education Research**

- **What it contains:** Curated summaries of best practices from AI education research, including common misconceptions, effective scaffolding strategies, and ethical frameworks (e.g., IMPACT audit).
- **Why needed:** Provides Sage with pedagogical grounding beyond the CollaborAITE course materials.
- **How added:** Uploaded to RAG knowledge base by instructor/developers.
- **Freshness:** Updated each semester based on new research and course feedback.
- **Licensing:** Open educational resources and original summaries of research.

**External Data Source: Agent Tool Documentation**

- **What it contains:** Current documentation for Claude Code, MCP, and other agent tools.
- **Why needed:** Sage needs accurate, up-to-date information about tool capabilities to teach effectively.
- **How added:** Web search tool (already available on CollaborAITE) or periodic RAG updates.
- **Freshness:** Real-time via web search for specific queries; quarterly RAG refresh for core concepts.

---

### **4d. Human-Agent Collaboration Flow**

**[Link to editable diagram: TBD]**

**Task Flow:**

1. **Learner initiates:** @sage "I'd like to learn how to use AI agents better"
   - Sage responds with warm greeting and diagnostic questions

2. **Diagnosis phase:**
   - Sage asks 2-3 questions to assess level (beginner/intermediate/advanced)
   - Sage reviews user's CollaborAITE profile and prior AI interactions
   - Sage recommends track (Using Agents or Building Agents)

3. **Exercise phase:**
   - Sage presents interactive exercise (e.g., "Classify these 3 tools as chatbot, agent, or automation")
   - Learner responds with attempt
   - Sage provides immediate feedback (not just correct/incorrect, but *why*)

4. **Coaching phase:**
   - If learner struggles, Sage offers hints via Socratic questioning
   - If learner succeeds, Sage offers stretch challenge

5. **Reflection phase:**
   - Sage prompts: "What did you learn? How will you apply this?"
   - Learner reflects; Sage acknowledges and connects to prior learning

6. **Progression:**
   - Sage updates learner's progress profile
   - Recommends next exercise or offers choice

**Control Points:**
- Learner can always ask for explanation, skip exercise, or change track
- Learner can request to see peer examples or work solo
- Learner can ask for ethical considerations at any point

**Threaded Plans:**
- For multi-step exercises, Sage presents plan in thread
- Each step shown separately with learner approval before proceeding

---

### **4e. Example Interactions**

---

**Interaction 1: Beginner Exploring AI Agents**

**Learner Context:** First-year student, computer science major, heard about Claude Code in class but confused about what AI agents actually are.

```
@student: @sage I'm confused about AI agents. What makes them different from ChatGPT?

@sage: Great question! Before I explain, let me ask: have you used ChatGPT or similar tools before? And what's one task you wish an AI could do automatically for you?

@student: Yeah I use ChatGPT for homework. I wish it could find and organize my research papers for me.

@sage: Perfect! That's actually a great example of the difference. Let me show you three scenarios—tell me which sounds most like what you just described:

**Scenario A:** You ask "find papers on climate change" and it gives you a list of papers it knows about.

**Scenario B:** You ask "organize my research" and it searches your files, reads them, categorizes by topic, and updates your bibliography.

**Scenario C:** You set up a script that runs every Monday, searches for new papers, and emails you a summary.

Which one sounds like what you want?

@student: Scenario B sounds amazing! That's what I want.

@sage: Exactly! Scenario B is an **AI agent**—it uses tools (file search, reading, categorizing) and takes actions to accomplish a goal. Scenario A is a chatbot (gives answers but doesn't act). Scenario C is automation (follows fixed rules).

Want to try an exercise where you identify which is which? It takes 2 minutes and will help solidify this.
```

**Data sources used:** User profile (beginner level), course materials (AI agent definitions from class slides).

---

**Interaction 2: Intermediate Learner Practicing Verification**

**Learner Context:** Junior student, has used Claude Code for debugging, working on a group project, just accepted an agent's code change without reviewing.

```
@student: @sage I just accepted a bunch of code changes from Claude without really reading them. Is that bad?

@sage: Thanks for sharing that—it's actually a common situation, and the fact that you're asking shows good instincts. Let me ask: what happened after you accepted the changes? Did everything work?

@student: Mostly, but there was one bug I had to fix later. I should have caught it.

@sage: Exactly. Here's the thing: AI agents are collaborators, not oracles. They're helpful but not infallible. Want to practice reviewing agent output? I have an exercise where you look at some code changes and identify what you'd check before accepting.

@student: Sure, that would help.

@sage: **Exercise: Spot the Issue**

Here's what an AI agent produced when asked to "add user authentication":

[Code snippet showing a login endpoint with potential SQL injection vulnerability]

What issues do you see? Take your time—there are at least 3 concerns.

@student: Hmm, the password is stored in plain text? And there's no input validation?

@sage: Excellent catches! You're thinking like a good collaborator now. The plain text storage is definitely a problem. There's also an SQL injection risk where the query is built with string concatenation. And a subtle one: no rate limiting, which could allow brute force attacks.

Before accepting AI-generated code, always check: security, edge cases, and whether it matches your project's patterns. Want another exercise, or shall we talk about how to prompt for better security from the start?

@student: How to prompt for security would be great.

@sage: Awesome! That's intermediate-level thinking—anticipating problems before they happen. Let me show you a technique...
```

**Data sources used:** Channel history (learner's prior AI interactions), course materials (security best practices from class).

---

**Interaction 3: Advanced Learner Exploring Ethics**

**Learner Context:** Graduate student, building an AI agent for a research project, concerned about bias and fairness.

```
@student: @sage I'm building an agent that helps grade student essays. I'm worried about bias—how do I make sure it's fair?

@sage: That's a deeply important question, and I'm glad you're asking it before deploying. Let's think through this systematically.

First, where might bias enter in an essay-grading agent? I can think of several points—what comes to mind for you?

@student: Maybe the training data? If it was trained on certain types of writing?

@sage: Exactly—training data is a major source. If the training essays were mostly from one demographic or academic background, the agent might systematically undervalue other styles. What else?

@student: The prompt I write? If I emphasize certain qualities?

@sage: Brilliant. Your prompt is essentially the rubric, and if it reflects your implicit preferences (formal language, certain argument structures), it could disadvantage students with different communication styles.

Here's a framework I find helpful: the **IMPACT audit**. Before deploying, ask:

- **I**ntent: What is this agent supposed to achieve?
- **M**easure: How will you know if it's working fairly?
- **P**eople: Who might be affected, especially at the margins?
- **A**lternatives: What are other ways to achieve the goal?
- **C**onsequences: What could go wrong, and for whom?
- **T**ransparency: How will users understand how decisions are made?

Want to work through an IMPACT audit for your grading agent? It might reveal some safeguards you haven't considered yet.

@student: Yes, let's do that. Starting with Intent...

@sage: Great! So: what's the core purpose of this agent? What problem is it solving that existing grading doesn't solve?

@student: I want to give students faster feedback on drafts so they can revise before final submission.

@sage: That's a valuable goal—formative feedback, not summative judgment. That already suggests some safeguards: it's advisory, not authoritative. Students can disagree. The stakes are lower.

But let's keep going. For **Measure**: How would you know if your agent is being fair? What would you look for?
```

**Data sources used:** External research (IMPACT framework), user profile (advanced level), course materials (ethics module).

---

### **4f. Harm Considerations**

| **Potential Harm** | **Likelihood** | **Design Safeguard** | **What If It Fails?** |
| :---- | :---- | :---- | :---- |
| **Accuracy harm:** Sage hallucinates course content or gives incorrect information about AI agents | Medium | All curriculum content grounded in RAG database; includes "I'm not sure" responses when confidence is low; instructor can review and correct content | Learner develops misconceptions; mitigation: error reporting mechanism, regular content audits |
| **Agency harm:** Learner becomes dependent on Sage, asking it to make decisions rather than developing own judgment | Medium | Socratic methodology designed to teach, not answer; explicit "teach me to fish" framing; reflection prompts emphasize learner's own thinking | Learner outsources cognition; mitigation: periodic "you try it solo" exercises, encourage peer discussion |
| **Equity harm:** Sage works better for some learners (e.g., those with better English, more prior experience) | Medium | Adaptive leveling based on demonstrated performance, not self-report; multiple example types (visual, textual, code); culturally diverse scenarios; translate mode if needed | Some learners left behind; mitigation: regular equity audits of completion and satisfaction data by demographic |

---

## **5. Technical Architecture and Design**

### Platform and Stack

- **Agent Framework:** Claude Agents SDK (for CollaborAITE integration)
- **Language:** Python
- **RAG:** CollaborAITE's built-in RAG database + curated external content
- **Tools:** Web search (for up-to-date agent documentation), sub-agent for exercise generation

### Major Modules

1. **Diagnostic Engine:** Assesses learner level through conversation and profile analysis
2. **Exercise Generator:** Creates personalized interactive exercises based on level and context
3. **Feedback Engine:** Provides Socratic hints and explanations, not just correct/incorrect
4. **Reflection Prompt:** Structures post-exercise reflection and records insights
5. **Progress Tracker:** Updates learner profile with demonstrated competencies

### Implementation Plan

**Week 1 (v1):**
- Basic conversational interface
- Diagnostic flow (3-question level assessment)
- 3 beginner exercises (What are agents? classification, basic prompting, tool identification)
- Simple feedback (correct/incorrect with brief explanation)

**Week 2 (v2):**
- Add reflection prompts
- Implement Socratic questioning for hints
- Add intermediate exercises (prompt improvement, output verification, multi-step workflows)
- Begin integration with CollaborAITE data sources (profile, channel history)

**Week 3 (evaluation):**
- Full evaluation with 2-3 learners
- Iterate based on feedback
- Add ethics-integrated exercises
- Implement threaded plan display

**Future (post-course):**
- Advanced track (building agents)
- Peer example surfacing
- Community features
- Multilingual support

---

## **6. Evaluation / Metrics of Success**

### **6a. Success Criteria**

| **Criterion** | **Observation Method** |
| :---- | :---- |
| Learners can accurately classify AI tools (chatbot vs. agent vs. automation) and explain the differences in their own words | Post-interaction assessment: learner explains classification to evaluator; compare pre/post accuracy |
| Learners demonstrate verification habits (checking agent output before accepting) in their actual CollaborAITE usage | Analyze channel logs: frequency of learner reviewing/editing agent suggestions vs. accepting blindly; survey self-reported habits |
| Learners can articulate an ethical consideration relevant to AI agent use (e.g., identifying bias, knowing when not to use AI) | Post-interaction interview: "Describe a situation where using an AI agent might be problematic"—code responses for ethical reasoning |

### **6b. Design Workshop Plan**

**What we'll demo:**
- 5-minute walkthrough of the diagnostic flow
- Live demonstration of 2-3 interactive exercises
- Sample reflection prompt and how Sage responds to learner reflection

**Questions for peers:**
1. Is the level-appropriate scaffolding clear? Would you know which track is for you?
2. Do the exercises feel like "real" practice, or too artificial?
3. Is the Socratic approach helpful or frustrating?
4. What ethical considerations are we missing?
5. Would you actually use this? When?

**Feedback capture:**
- Shared Google Doc for live notes during demo
- Structured feedback form (Likert + open response) for asynchronous input
- One team member dedicated to note-taking, others facilitating

### **6c. Mini-Evaluation Plan**

| **Element** | **Description** |
| :---- | :---- |
| **Participants** | 2-3 students from COS 598/498 or another course using CollaborAITE; mix of experience levels (one beginner, one intermediate) |
| **Task** | "Spend 15-20 minutes with Sage learning about AI agents. Try at least 2 exercises and complete one reflection. Think aloud as you work." |
| **Observation method** | Live observation via screen share; recording of interaction logs |
| **Feedback collection** | Short semi-structured interview (10 min): What worked? What was confusing? Would you use this again? What would make it better? |
| **Analysis** | Thematic analysis of interview transcripts; review of interaction logs for completion rates, error patterns, engagement markers |

### **6d. Final Evaluation Plan**

**Data to collect:**
- Interaction logs: exercises attempted, completion rates, time spent, hint requests
- Reflection content: themes in what learners report learning
- Pre/post self-assessment: confidence in using AI agents (1-10 scale)
- Channel observation: changes in learner's actual AI use patterns (more verification? better prompting?)

**Analysis:**
- Quantitative: completion rates, time-to-completion, accuracy trends
- Qualitative: themes in learner feedback, reflection content analysis
- Comparative: learners who used Sage vs. similar learners who didn't

**Deployment decision criteria:**
- Deploy if: 70%+ completion rate on exercises, positive qualitative feedback, observable behavior change in AI use
- Iterate if: High dropout rates, confusion about purpose, negative feedback on pedagogical approach
- Deprecate if: No meaningful learning outcomes, learners prefer other resources, maintenance burden exceeds value

---

*Specification Version 1.0 · Group 10 · April 2026*
