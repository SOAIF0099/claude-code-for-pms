# Firecrawl

> Research competitors, read documentation, and gather web data without leaving your terminal.

## What It Does

Firecrawl is a web research tool that lets you search the web, scrape pages, and extract structured data directly from Claude Code. It handles JavaScript-rendered pages, bypasses common blocks, and returns clean markdown optimized for AI context. Think of it as having a research assistant that can read any webpage and summarize it for you.

For PMs, this means competitive analysis, market research, and documentation lookups happen in the same session where you're doing everything else.

## When to Use It (PM Scenarios)

- Researching competitor features and pricing pages
- Reading API documentation or technical specs for a vendor evaluation
- Gathering data for a business case or market analysis
- Checking what's been published about your product or industry
- Extracting content from multiple pages for a comparison table

## How to Use It

### Step 1: Install Firecrawl

```bash
npm install -g firecrawl
```

### Step 2: Authenticate

```bash
firecrawl login --browser
```

This opens your browser to get an API key. The key is stored automatically.

### Step 3: Use It in Claude Code

Once installed, just ask Claude to research something. The skill activates automatically for any web-related task:

```
Research the top 5 competitors in the digital product passport space.
Scrape their pricing pages and summarize the differences.
```

### Key Commands

**Search the web:**
```bash
firecrawl search "digital product passport pricing" --scrape
```

**Scrape a specific page:**
```bash
firecrawl scrape "https://competitor.com/pricing" --format markdown
```

**Map all URLs on a site:**
```bash
firecrawl map "https://competitor.com" --limit 50
```

## Example Prompt

```
I need a competitive analysis of DPP platforms in the EU textile space.
Search for companies offering digital product passport solutions,
scrape their homepages and pricing pages, and give me a comparison
table with features, pricing, and target market.
```

Claude will use Firecrawl to search, scrape multiple sites, and compile the results into a structured comparison.

## Pro Tips

- Firecrawl handles JavaScript-heavy sites that normal scrapers can't read. SPAs, dashboards behind public pages, dynamic content, it all works.
- Use `--scrape` with search to get full page content, not just snippets. This gives Claude much better context for analysis.
