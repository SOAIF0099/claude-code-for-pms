# Systematic Debugging

> Find root causes with a scientific method instead of guessing and hoping.

## What It Does

This skill enforces a 4-phase debugging process: investigate, analyze patterns, form a hypothesis, then implement a fix. No one is allowed to propose a fix until the root cause is understood. If three fixes fail in a row, the skill forces you to step back and question the architecture instead of trying a fourth patch.

For PMs, this means bugs get fixed properly the first time instead of bouncing back from QA three times.

## When to Use It (PM Scenarios)

- A critical bug is reported and you need it fixed right, not fast-then-wrong
- A fix was deployed but the bug came back (symptom was treated, not the cause)
- The team is stuck on a bug that "makes no sense"
- You want to understand why something broke, not just that it was fixed

## How to Use It

### Step 1: Install the Superpowers Plugin

```bash
claude install @anthropic/claude-code-superpowers
```

### Step 2: Describe the Bug

Give Claude the bug report. Include error messages, logs, screenshots, or steps to reproduce:

```
Users are seeing a blank screen after clicking "Submit Order."
It started after yesterday's deploy. Here's the error from the console:
TypeError: Cannot read properties of undefined (reading 'id')
```

### Step 3: Watch the 4 Phases

**Phase 1 - Investigation:** Claude reads error messages, reproduces the bug, checks recent commits, and traces the data flow.

**Phase 2 - Pattern Analysis:** Claude finds working examples in the codebase, compares them against the broken code, and identifies every difference.

**Phase 3 - Hypothesis:** Claude states a specific hypothesis: "The root cause is X because Y." Then tests it minimally.

**Phase 4 - Implementation:** Claude writes a failing test that reproduces the bug, implements the fix, and verifies the test passes.

### What This Prevents

The skill blocks these common anti-patterns:

- "Quick fix for now, investigate later" (no, investigate now)
- "Just try changing X and see if it works" (no, understand why first)
- "It's probably X, let me fix that" (no, verify the hypothesis)
- Three failed fixes in a row without stepping back (stop, rethink the approach)

## Example Prompt

```
There's a race condition in our notification system. Sometimes users
get duplicate notifications. The team has tried fixing it twice but
it keeps coming back. Debug this systematically.
```

## Pro Tips

- Paste the actual error logs, not a summary. Claude's investigation is only as good as the data you provide.
- If Claude finds the root cause is architectural (not just a code bug), take that seriously. Some bugs can't be fixed with patches.
