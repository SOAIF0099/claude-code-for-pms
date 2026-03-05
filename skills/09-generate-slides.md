# Generate Slides

> Create magazine-quality slide decks as self-contained HTML pages from any content.

## What It Does

This skill turns markdown content, strategy documents, or plain descriptions into a fully styled HTML slide deck. Each slide fills exactly one viewport (no scrolling), uses presentation-grade typography, and includes visual elements like diagrams, charts, and SVG accents. The output is a single HTML file that works in any browser, no PowerPoint needed.

For PMs, this is how you go from "I have a doc" to "I have a presentation" in minutes, not hours.

## When to Use It (PM Scenarios)

- You have a strategy document and need a slide deck for leadership
- You need to present a project update and want it to look polished
- You're running a workshop and need visual slides, not bullet-point walls
- You wrote a design doc and need to present it to the team
- You want a quick deck for a client call without opening PowerPoint

## How to Use It

### Step 1: Install the Skill

```bash
claude install @anthropic/claude-code-skills
```

### Step 2: Ask for Slides

Provide the content source and ask Claude to generate slides:

```
/generate-slides

Turn my product strategy doc at docs/strategy-q2.md into a
presentation deck. Focus on the diagnosis, key decisions,
and roadmap sections.
```

### Step 3: Review in Browser

Claude generates an HTML file and opens it in your browser. Navigate between slides with arrow keys or click.

### Slide Aesthetics

Claude picks from tasteful presets:

| Preset | Vibe |
|--------|------|
| Midnight Editorial | Dark background, serif headlines, gold accents |
| Warm Signal | Light cream tones, terracotta and sage colors |
| Terminal Mono | Dark terminal aesthetic, monospace, green accents |
| Swiss Clean | White background, sans-serif, minimal color |

You can request a specific one or let Claude choose based on your content.

### What You Get

- Title slide with your name/company
- Section dividers between major topics
- Content slides with clear hierarchy
- Diagram slides (Mermaid-rendered) for architecture or flows
- Data slides with inline charts
- All content from your source doc, nothing gets dropped

## Example Prompt

```
I need a slide deck for tomorrow's board meeting.
Use the quarterly update at docs/q1-update.md as the source.
Keep it under 12 slides. Midnight Editorial style.
Include the revenue chart and the product roadmap timeline.
```

## Pro Tips

- The HTML slides work great on any screen. Present directly from your browser in fullscreen mode (F11).
- Since it's just an HTML file, you can version it in git, share it via link, or host it anywhere.
