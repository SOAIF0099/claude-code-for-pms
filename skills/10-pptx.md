# PPTX Generator

> Generate PowerPoint files from markdown when you need a .pptx, not an HTML page.

## What It Does

This skill converts markdown documents into properly formatted PowerPoint presentations. It parses your document structure, extracts key sections based on headers, and produces a .pptx file you can open in PowerPoint, Google Slides, or Keynote. The output is professional and ready to share.

While the Generate Slides skill (Skill 09) creates HTML decks for browser presentations, this one produces actual .pptx files for when you need to email a deck, upload it to a shared drive, or use a tool that only accepts PowerPoint format.

## When to Use It (PM Scenarios)

- You need to send a deck to a client or stakeholder who expects .pptx format
- Your company uses Google Slides or PowerPoint and you need a compatible file
- You want to generate a first draft of a deck that your team can then edit in PowerPoint
- You're creating a template deck that others will customize

## How to Use It

### Step 1: Prerequisites

You need Python with the `python-pptx` library:

```bash
pip install python-pptx
```

### Step 2: Prepare Your Content

Write your content as a markdown file with clear headers (`##` for slide titles). Or just describe what you want:

```
Generate a PowerPoint presentation from my strategy document
at docs/product-strategy.md. Include the diagnosis, guiding
policy, and roadmap sections.
```

### Step 3: Get Your .pptx

Claude reads your markdown, identifies the key sections, and generates a Python script that creates the PowerPoint file. The output .pptx file lands in your project directory.

### What Gets Converted

| Markdown Element | PowerPoint Element |
|------------------|--------------------|
| `## Header` | Slide title |
| Bullet points | Slide bullet content |
| Nested bullets | Indented sub-points |
| Bold text | Bold formatting |
| Sections | Slide breaks |

## Example Prompt

```
I have a quarterly business review document at docs/qbr-q1.md.
Generate a PowerPoint deck from it. Focus on the executive summary,
key metrics, risks, and next quarter plan sections.
Save it as qbr-q1-2025.pptx.
```

Claude parses the document, extracts the relevant sections, and produces a ready-to-use PowerPoint file.

## Pro Tips

- Use this for the first draft, then polish in PowerPoint. The generated deck handles structure and content; you add the visual polish your brand requires.
- If you need a visually stunning deck and don't care about .pptx format, use Generate Slides (Skill 09) instead. It produces much richer visual output.
