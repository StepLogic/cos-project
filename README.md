# AI Tutor Agent

An AI agent built with Claude Skills that teaches people how to **use** and **build** AI agents — with interactive practice, guided reflection, and ethical AI education.

## Learning Tracks

### Track 1: Using AI Agents
Learn to work with AI agents effectively: prompting, understanding tools, reviewing output, and multi-step collaboration.

**Modules:**
1. What Are AI Agents? (Beginner)
2. Prompting AI Agents (Beginner)
3. Working With Agent Tools (Intermediate)
4. Advanced Agent Collaboration (Advanced)

### Track 2: Building AI Agents
Learn to design, build, test, and deploy AI agents responsibly.

**Modules:**
1. Agent Architecture Fundamentals (Beginner)
2. Building Your First Agent (Intermediate)
3. Testing and Reliability (Intermediate)
4. Ethics and Responsible AI Building (Advanced)

## Project Structure

```
skills/           # Claude Skills defining tutor behavior
  ai-tutor-router.md       # Main entry point
  ai-tutor-onboard.md      # New user assessment
  ai-tutor-use-agents.md   # Track 1: Using agents
  ai-tutor-build-agents.md # Track 2: Building agents
  ai-tutor-practice.md     # Interactive exercises
  ai-tutor-reflect.md      # Feedback & reflection
  ai-tutor-ethics.md       # Ethical AI thinking

data/             # Curricula, exercises, and example data
  users/          # Example user profiles and progress schema
  curricula/      # Lesson sequences for each track
  exercises/      # Practice exercises
  examples/       # Annotated interaction examples
```

## Running the Agent

### Prerequisites

- [Claude Code](https://claude.ai/code) installed and authenticated
- Git repository cloned locally

### Option 1: Run with Skills (Recommended)

From the project root directory, load the skills and start a conversation:

```bash
# Navigate to the project directory
cd /path/to/cos-project

# Ensure skills are loaded in Claude Code
# The skills should auto-load from the .claude/skills/ directory

# Start Claude Code
claude
```

Once in Claude Code, invoke the AI Tutor by describing what you want to learn:

```
> I want to learn how to build an AI agent
> Help me understand how to use AI agents effectively
> Can I practice what I learned about prompting?
```

### Option 2: Run with Direct Skill Invocation

You can invoke specific skills directly:

```bash
claude skill ai-tutor-router
```

Or for a specific track:

```bash
claude skill ai-tutor-build-agents
claude skill ai-tutor-use-agents
```

### Option 3: Role-Play with a Persona

To test the agent with a specific learner persona (e.g., Kojo, Maya, David, Jordan):

```
> I am Kojo Asante, a professor at KNUST. I'd like to explore how AI agents might help my students.
```

See `data/personas/` for available personas.

### Development: Testing Changes

After modifying skills, reload them in Claude Code:

```
> /reload-plugins
```

## Design Principles

1. **Meet learners where they are** — Adapt to beginner, intermediate, and advanced levels
2. **Teach, don't do** — Guide understanding through questions and practice, not answers
3. **Ethics throughout** — Ethical thinking is woven into every lesson, not siloed
4. **Warm and encouraging** — Supportive, patient persona that celebrates genuine progress
5. **Interactive** — Every concept has a practice exercise; learning happens by doing
