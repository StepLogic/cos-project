# Session Context

## User Prompts

### Prompt 1

Base directory for this skill: /Users/elvisgyaase/.claude/plugins/cache/claude-plugins-official/superpowers/5.0.7/skills/writing-plans

# Writing Plans

## Overview

Write comprehensive implementation plans assuming the engineer has zero context for our codebase and questionable taste. Document everything they need to know: which files to touch for each task, code, testing, docs they might need to check, how to test it. Give them the whole plan as bite-sized tasks. DRY. YAGNI. TDD. Frequent c...

### Prompt 2

Using only the skills available to you (YOU MUST USE THE SKILLS), use the session-start skill to respond to the following prompt from a user of the AI agent system this project prototypes. YOU MAY ONLY USE THE SKILLS AND MAY NOT READ ANY OTHER FILES TO PREPARE OR DECIDE ON A RESPONSE.  "I am kojo I want to build an agent to assist me in my robotics research.I need an agent to assist me in my lietrature review"

### Prompt 3

1) Never  2) all the above

### Prompt 4

All the above

### Prompt 5

Create and save the relevant skills in the skils folder

### Prompt 6

Write/generate at least 4 JSON persona files in data/personas/ representing realistic, diverse users. Each persona should include: name, age, backstory, emotional triggers, existing strengths, and what success looks like. Creat Maya ( a new phd student with imposter syndrome), David (a 3rd year phd student trying to find a problem to work), Kojo (a professor advicing an undergraduate researcher in robotics), and Jordan (Hard-nosed Reviewer from Top robotics conferencers).

### Prompt 7

I am kojo i want to start a project on robotic manipulation

### Prompt 8

I am persona Kojo - i would to like to build an agent to assist me in reseaching into tobotic manipulation -

### Prompt 9

I am not certain what are the areas i can jump into

### Prompt 10

log kojos conversation into data/interactions/actual-logs as kojo-convervation-topic-number.md

### Prompt 11

Ask Claude Code to create skills based on your description. Each skill becomes a file at .claude/skills/<skill-name>/SKILL.md — a markdown file with YAML frontmatter (name, description) and detailed prompt instructions.

