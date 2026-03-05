# Subagent-Driven Development

> Execute implementation plans with automatic quality checks between every task.

## What It Does

This skill takes an implementation plan and executes it task by task, using fresh "subagents" (isolated Claude instances) for each task. After every task, two reviewers check the work: one for spec compliance ("did it build what was asked?") and one for code quality ("is it built well?"). Issues get fixed before moving to the next task.

For PMs, this is like having a developer, a QA engineer, and a code reviewer working in a tight loop, all in one terminal session.

## When to Use It (PM Scenarios)

- You have an implementation plan (from Skill 02) and want Claude to execute it
- You want automatic quality gates between each piece of work
- You're running a session where you need to see progress in real time
- You want to catch issues early instead of finding them in code review days later

## How to Use It

### Step 1: Install the Superpowers Plugin

```bash
claude install @anthropic/claude-code-superpowers
```

### Step 2: Have a Plan Ready

You need an implementation plan (from the writing-plans skill). Either:
- Point Claude to the plan file: `docs/plans/2025-03-01-feature-plan.md`
- Or paste the plan directly into the conversation

### Step 3: Choose Subagent-Driven Execution

When the writing-plans skill finishes, it asks how you want to execute. Choose **"Subagent-Driven (this session)"**.

Or trigger it directly:

```
Execute the plan in docs/plans/2025-03-01-feature-plan.md
using subagent-driven development.
```

### Step 4: Watch the Loop

For each task, you'll see:
1. **Implementer** builds the feature and runs tests
2. **Spec reviewer** checks if it matches the plan
3. **Quality reviewer** checks code quality
4. If either reviewer finds issues, the implementer fixes them
5. Move to next task

### Step 5: Final Review

After all tasks are done, a final comprehensive code review runs across the entire implementation.

## Example Prompt

```
I have the billing implementation plan ready at
docs/plans/2025-03-01-billing-plan.md.
Execute it with subagent-driven development.
I'll be here to answer questions if anything is unclear.
```

## Pro Tips

- Stay in the session. If a subagent has a question about requirements, it surfaces it to you immediately. Quick answers keep the flow going.
- The two-stage review (spec first, quality second) is intentional. There's no point polishing code that doesn't meet the spec.
