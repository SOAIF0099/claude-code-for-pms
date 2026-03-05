# Visual Explainer

> Generate beautiful, self-contained HTML diagrams to explain systems, architecture, and data.

## What It Does

This skill creates polished, interactive HTML pages that visually explain technical concepts. Instead of ASCII diagrams or rough whiteboard sketches, you get properly styled architecture diagrams, flowcharts, data flow visualizations, comparison tables, and dashboards. The output is a single HTML file you can open in any browser and share with anyone.

For PMs, this is how you make technical concepts accessible to non-technical stakeholders. Need to explain the system architecture to your CEO? Need a visual for a client presentation? This handles it.

## When to Use It (PM Scenarios)

- You need to explain your product's architecture to a non-technical stakeholder
- You're creating a visual for a presentation or document
- You want to compare multiple options in a clear, visual format
- You need a diagram of a user flow, data pipeline, or system interaction
- You're documenting a complex process and text alone isn't cutting it

## How to Use It

### Step 1: Install the Skill

```bash
claude install @anthropic/claude-code-skills
```

### Step 2: Describe What You Need

Ask Claude for a visual explanation of anything:

```
Create a visual diagram showing how our authentication flow works,
from the user clicking "Sign In" to landing on the dashboard.
```

### Step 3: Get Your HTML Page

Claude generates a self-contained HTML file with:
- Professional typography and color schemes
- Interactive elements (zoom, hover states)
- Dark/light mode support
- No external dependencies (works offline)

The file opens automatically in your browser.

### Diagram Types Available

| Type | Best For |
|------|----------|
| Architecture diagram | System overview, service interactions |
| Flowchart | User flows, decision trees, processes |
| Sequence diagram | API calls, service communication over time |
| Data flow | How data moves through your system |
| Comparison table | Evaluating options, vendor comparisons |
| Timeline | Project roadmaps, release history |
| Dashboard | Metrics overview, KPI visualization |
| State machine | Feature states, workflow stages |
| Mind map | Brainstorming outputs, feature mapping |

## Example Prompt

```
Create a visual architecture diagram of our system:
- Next.js frontend on Vercel
- Supabase for auth and database
- Stripe for billing
- Resend for emails
Show how data flows between these services when a user
upgrades their plan.
```

Claude produces a clean, styled diagram showing all the services, data flows, and interaction points.

## Pro Tips

- These HTML files are fully self-contained. Email them, drop them in Notion, attach them to tickets. They just work.
- Ask for specific aesthetics: "editorial style with earth tones" or "clean and minimal with lots of whitespace." Claude adapts the design.
