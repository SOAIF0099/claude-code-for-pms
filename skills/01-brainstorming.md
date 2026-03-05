# Brainstorming

> Turn vague ideas into validated designs before anyone writes a line of code.

## What It Does

This skill forces a structured design conversation before any implementation begins. You describe what you want to build, and Claude walks you through clarifying questions (one at a time), proposes 2-3 approaches with trade-offs, and produces a documented design that your team can review.

No code gets written until the design is approved. This prevents the classic PM pain of developers building the wrong thing because the spec was unclear.

## When to Use It (PM Scenarios)

- You have a feature idea but haven't fully thought through the edge cases
- You need to evaluate multiple approaches before committing to one
- You want a written design doc to share with your engineering team
- You're about to kick off a sprint and need clear specs

## How to Use It

### Step 1: Install the Superpowers Plugin

```bash
claude install @anthropic/claude-code-superpowers
```

### Step 2: Start a Conversation

Open Claude Code in your project directory and describe what you want to build:

```
claude
```

Then type your idea. The skill activates automatically when Claude detects creative or feature work.

### Step 3: Answer the Questions

Claude will ask you one question at a time. Most are multiple choice. Be honest when you don't know the answer yet, that's what this process is for.

### Step 4: Review the Design

Claude presents a design in sections. After each section, it asks if it looks right. Say no if something feels off.

### Step 5: Get Your Design Doc

Once approved, Claude saves the design to `docs/plans/YYYY-MM-DD-<topic>-design.md` in your project.

## Example Prompt

```
I want to add a self-serve onboarding flow for new customers.
They should be able to sign up, pick a plan, and start using the product
without talking to sales.
```

Claude will ask things like:
- "Who is the target user? (a) Individual contributors, (b) Team leads, (c) Both?"
- "What plans should be available at launch?"
- "Should there be a free trial or freemium tier?"

And eventually produce a complete design doc with architecture decisions, data flow, and components.

## Pro Tips

- Don't skip the questions to rush to implementation. The 10 minutes you spend here save hours of rework.
- If you already have a PRD, paste it into the conversation. Claude will use it as context and ask sharper questions.
