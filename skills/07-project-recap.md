# Project Recap

> Rebuild your mental model of any project's current state, recent decisions, and problem areas.

## What It Does

This skill generates a visual HTML page that summarizes where a project stands right now. It reads the codebase, recent git history, open issues, and documentation to produce a structured overview: what was built, what decisions were made, what's in progress, and where the cognitive debt is piling up.

For PMs, this is the "get me up to speed" button. Whether you're returning from vacation, switching between projects, or onboarding someone new, this gives you the full picture in one page.

## When to Use It (PM Scenarios)

- You're switching context between multiple projects and need a quick refresh
- A new team member needs to understand the project's current state
- You haven't touched a project in weeks and need to remember where things stand
- You want to identify what areas of the project need the most attention
- Preparing for a status update or stakeholder meeting

## How to Use It

### Step 1: Install the Visual Explainer Skill

Project Recap is part of the visual-explainer skill family. Add it to your Claude Code skills:

```bash
# Add the skill to your project's CLAUDE.md or install via plugin
claude install @anthropic/claude-code-skills
```

### Step 2: Ask for a Recap

Navigate to your project directory and ask Claude:

```
Give me a project recap. What's the current state of this project?
```

Or use the slash command:

```
/project-recap
```

### Step 3: Review the Visual Output

Claude generates a self-contained HTML page and opens it in your browser. The page includes:

- **Project overview**: What this project is, tech stack, key files
- **Recent activity**: Last commits, what changed, who worked on what
- **Current state**: What's built, what's in progress, what's blocked
- **Decision log**: Recent architectural or product decisions
- **Cognitive debt hotspots**: Areas of the codebase that are complex, frequently changed, or under-documented

## Example Prompt

```
I haven't looked at this project in two weeks. Give me a full project
recap so I can get back up to speed before tomorrow's sprint planning.
```

Claude scans the repo, reads recent commits and docs, and produces a visual summary you can review in 5 minutes.

## Pro Tips

- Run this at the start of every week for each active project. It's faster than reading through Slack history and Jira tickets.
- The HTML output is self-contained. You can share it with stakeholders or attach it to a status update.
