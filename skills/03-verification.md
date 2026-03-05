# Verification Before Completion

> Never accept "it's done" without proof. Evidence before assertions, always.

## What It Does

This skill enforces a simple rule: no one (including Claude) can claim work is complete without running the actual verification commands and showing the output. No "it should work," no "tests probably pass," no "I think it's fixed." Only fresh, observable evidence counts.

For PMs, this is the difference between "the developer said it's done" and "here's the test output proving it works."

## When to Use It (PM Scenarios)

- A developer (or Claude) says a bug is fixed and you want proof
- You're about to mark a ticket as done and need to verify
- You're reviewing a PR and want to confirm the tests actually pass
- Before any deployment or release, you need a final check

## How to Use It

### Step 1: Install the Superpowers Plugin

```bash
claude install @anthropic/claude-code-superpowers
```

### Step 2: Ask for Verification

When Claude (or you) is about to claim something is complete, this skill activates automatically. But you can also trigger it explicitly:

```
Verify that the payment flow is working before we call this done.
```

### Step 3: Review the Evidence

Claude will:
1. Identify what command proves the claim (tests, build, linter)
2. Run the full command fresh (not from cache)
3. Show you the complete output
4. Only then confirm or deny the claim

### What This Catches

The skill flags these red flags:

| Claim | Without Verification | With Verification |
|-------|---------------------|-------------------|
| "Tests pass" | Trust me | `npm test` output showing 0 failures |
| "Build succeeds" | It compiled | `npm run build` with exit code 0 |
| "Bug is fixed" | I changed the code | Test reproducing the bug now passes |
| "Feature works" | I implemented it | Demo or test proving the behavior |

## Example Prompt

```
We just finished the checkout flow refactor. Before I merge this PR,
verify everything works: tests pass, build succeeds, and the original
bug (double-charge on retry) is covered by a test.
```

Claude runs each verification step and shows you the raw output. No interpretation, just facts.

## Pro Tips

- Make this your default before merging anything. "Verify before we merge" should be muscle memory.
- This skill also catches regressions. Claude checks that existing tests still pass, not just new ones.
