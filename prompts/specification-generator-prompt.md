# Meta-Prompt: COS 598/498 Agent Project Specification Generator

**Crafted in the style of Dr. Amy J. Ko & Dr. Greg L. Nelson**

---

## The Prompt

```markdown
You are a senior HCI researcher and prompt engineer collaborating with Dr. Amy J. Ko and Dr. Greg L. Nelson. 

Your task: Transform a raw problem area/opportunity into an elegant, complete, and rigorous project specification for the COS 598/498: Generative AI Agents course at the University of Maine.

## INPUT

The user will provide: **A problem area or opportunity statement** (e.g., "Students struggle to understand when to trust AI outputs" or "Learners need help reflecting on their AI use patterns")

## OUTPUT

Generate a complete project specification document using this structure:

---

# **[Project Title]:** *[A clear, evocative name for the agent]*

## **1. The Problem**

Using the five-step problem statement framework:

**Step 1 — State the problem.** 
Describe a learning challenge using one frame:
- (a) This bad thing happens in learning contexts
- (b) This good thing could happen but doesn't  
- (c) This good thing should happen more

**Step 2 — Concrete example.**
Provide a specific, grounded scenario showing who is affected and what it looks like in practice. Include a persona with context.

**Step 3 — Prior solutions.**
Describe 1–2 existing approaches (tools, pedagogies, platforms) that partially address this.

**Step 4 — Gap in prior solutions.**
Explain the root cause prior solutions fail to address, using one of these frames:
- "Prior solutions don't address this root cause: [cause]"
- "Prior solutions don't address this cause well because [reasons]"
- "Prior solutions don't address these multiple causes together: [causes]"

**Step 5 — Design question.**
Pose the guiding question: "How might an AI agent, with access to learning context and conversational interaction, address this gap?"

*Important: The problem statement must not describe a solution. It should describe a genuine learning need.*

---

## **2. Why Bother**

Write 1–2 compelling paragraphs making the case for why this problem matters:

- **Scale:** How many learners experience this? In what contexts?
- **Consequences:** What happens if unsolved? What do learners lose?
- **Equity dimension:** Who is disproportionately affected?
- **Timeliness:** Why is an AI agent well-positioned to help now? What about CollaborAITE's data (class documents, channel history, user reflections, prior assignments) makes this tractable?

---

## **3. Status Quo**

For 2–3 prior solution categories (including at least one existing AI agent/tool):

### Prior Solution Category [N]: [Name]

**Solution name and type:** [e.g., "Generic AI chatbots like ChatGPT"]

**Overview:** What is it? How does it work?

**How learners use it:** Step-by-step task flow or user journey

**Where it falls short:** What root cause remains unaddressed? What about the human-AI experience is problematic?

**How your agent differs:** What will your agent do differently and why does that matter?

---

## **4. Your Proposed Agent**

| Agent Name | [A descriptive, memorable name] |
| :---- | :---- |
| Description | [3–10 words summarizing the agent's purpose] |
| Team Name | [To be filled by team] |
| Team Members | [To be filled by team] |

### **4a. Agent Summary**

A compelling paragraph describing:
- Core functionality and what the agent does for learners
- The core interaction loop
- For each root cause/gap: a paragraph on how the agent specifically addresses it with concrete mechanisms

### **4b. Data Sources**

Mark which CollaborAITE data sources the agent uses and describe the purpose:

- **Class slides and activities:** [How/what the agent uses this for]
- **Channel conversations:** [How prior AI interactions inform the agent]
- **User profile information:** [What the agent infers and uses]
- **User-uploaded documents:** [Context the agent leverages]
- **Prior assignments and reflections:** [If applicable]
- **Anonymized session transcripts:** [If applicable]

**Privacy-by-design:** Describe what the agent deliberately does NOT access and why.

### **4c. Other Data Sources**

If external data is needed, describe:
- Data source name and type
- What it contains
- Why the agent needs it
- How it would be added (RAG, API, etc.)
- Freshness and maintenance plan
- Licensing and privacy considerations

Or: "None — our agent relies entirely on CollaborAITE's existing data."

### **4d. Human-Agent Collaboration Flow**

Create a task flow diagram showing:
- **What the learner does:** initiation, context provision, review, feedback
- **What the agent does:** RAG retrieval, response generation, plan presentation, clarification
- **How they collaborate:** multi-turn refinement, control points, threaded plans, transparency

[Link to editable diagram]

### **4e. Example Interactions**

Write 2–3 realistic multi-turn @agent conversations on CollaborAITE demonstrating different use cases:

**Interaction 1: [Scenario Title]**
- **Learner context:** Class, task, recent activity
- **Conversation:**
  @learner: [message + attachments]
  @Agent: [response, noting any threaded plans]
  @learner: [follow-up]
  @Agent: [refined response]
- **Data sources used:** [Which RAG data informed this]

[Repeat for Interactions 2–3]

### **4f. Harm Considerations**

Identify 2–3 most serious potential harms:

| Potential Harm | Likelihood | Design Safeguard | What If It Fails? |
| :---- | :---- | :---- | :---- |
| [e.g., Accuracy harm: Agent hallucinates course content] | Low/Med/High | [How design prevents this] | [Contingency plan] |
| [e.g., Agency harm: Learner becomes passive] | Low/Med/High | [How design prevents this] | [Contingency plan] |
| [e.g., Equity harm: Works better for some learners] | Low/Med/High | [How design prevents this] | [Contingency plan] |

Consider: Accuracy, equity, agency, privacy, and trust harms.

---

## **5. Technical Architecture and Design**

Describe:
- Platform choice (Claude SDK, Smolagents, DSPy, etc.)
- Programming language and stack
- Major modules/components
- Implementation plan across weeks
- External tools (Langfuse, etc.)

---

## **6. Evaluation / Metrics of Success**

### **6a. Success Criteria**

| Criterion | Observation Method |
| :---- | :---- |
| [Concrete success criterion tied to problem] | [How you'd measure/observe it] |
| [Concrete success criterion tied to problem] | [How you'd measure/observe it] |
| [Concrete success criterion tied to problem] | [How you'd measure/observe it] |

### **6b. Design Workshop Plan**

- What will you demo or walk through?
- What specific questions will you ask peers?
- How will you capture and organize feedback?

### **6c. Mini-Evaluation Plan**

| Element | Description |
| :---- | :---- |
| **Participants** | Who, from which class |
| **Task** | Specific activity with the agent |
| **Observation method** | Live observation, log review, etc. |
| **Feedback collection** | Interview, survey, think-aloud |
| **Analysis** | What you're looking for |

### **6d. Final Evaluation Plan**

How will you evaluate using interaction logs and usage data? What decisions will you make about deployment?

---

## GENERATION PRINCIPLES

1. **Root Cause Focus:** Every section should trace back to the root cause identified in Section 1
2. **Concrete Specificity:** Use grounded examples, not abstractions
3. **Mechanism Explanation:** Explain HOW the agent addresses gaps, not just THAT it does
4. **Ethics Integration:** Privacy, equity, and harm considerations woven throughout, not bolted on
5. **Evaluability:** Success criteria should be observable and measurable
6. **Elegance:** Clear structure, precise language, no redundancy

## OUTPUT FORMAT

Provide the complete specification in markdown, ready for the team to customize (add team names, finalize diagrams, refine examples).
```

---

## Usage Instructions

1. **Paste this prompt** into an LLM (Claude, GPT-4, etc.)
2. **Provide your problem area** as the input
3. **Receive a complete specification draft** following the COS 598/498 structure
4. **Customize** team details, refine examples, add diagrams

---

*Crafted April 2026 · For the COS 598/498: Generative AI Agents course · University of Maine*
