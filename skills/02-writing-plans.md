# Writing Plans

> Convert approved designs into detailed, step-by-step implementation tasks that any developer can execute.

## What It Does

This skill takes a design or spec and breaks it down into bite-sized tasks (2-5 minutes each). Every task includes exact file paths, complete code, test commands, and expected outputs. The plan assumes the person executing it has zero context about your codebase.

Think of it as writing the perfect ticket, except Claude writes it for you, with more detail than any human would bother to include.

## When to Use It (PM Scenarios)

- You have an approved design and need to break it into sprint tasks
- You want to hand off implementation to a developer (or to Claude) with zero ambiguity
- You need to estimate effort by seeing the exact scope of work
- You want a clear checklist to track progress against

## How to Use It

### Step 1: Install the Superpowers Plugin

```bash
claude install @anthropic/claude-code-superpowers
```

### Step 2: Have a Design Ready

This skill works best after brainstorming (Skill 01). You need either:
- A design doc from the brainstorming skill
- A PRD or spec you can paste in
- A clear description of what to build

### Step 3: Ask Claude to Plan

```
Write an implementation plan for the onboarding flow design
in docs/plans/2025-03-01-onboarding-design.md
```

### Step 4: Review the Plan

Claude produces a markdown document with numbered tasks. Each task has:
- Files to create or modify (exact paths)
- Complete code (not pseudocode)
- Test commands with expected output
- A commit message

### Step 5: Choose Execution Method

After the plan is written, Claude asks:

1. **Subagent-Driven** (same session): Claude executes tasks one by one with automatic code review between each
2. **Parallel Session** (separate window): You open a new Claude session and point it at the plan file

## Example Prompt

```
I need an implementation plan for adding Stripe billing to our Next.js app.
Users should be able to upgrade from free to paid, manage their subscription,
and see invoices. We use Supabase for the database.
```

Claude produces a plan like:

```markdown
### Task 1: Create Stripe webhook handler
Files:
- Create: src/app/api/webhooks/stripe/route.ts
- Create: tests/api/webhooks/stripe.test.ts

Step 1: Write the failing test...
Step 2: Run test to verify it fails...
Step 3: Write minimal implementation...
```

## Pro Tips

- Plans are saved to `docs/plans/` so your whole team can review them before implementation starts.
- The plan doubles as documentation. After the feature is built, you have a record of every decision and every file that was touched.
