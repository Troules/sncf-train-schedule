---
description: Summarize a YouTube video with chapters, timestamps, and markdown output
argument-hint: "<youtube-url>"
allowed-tools: ["mcp__plugin_sumYT_youtube-transcript__get_transcript", "Write", "WebSearch", "WebFetch"]
---

# /sumYT — YouTube Video Summarizer

User request: **"$ARGUMENTS"**

## Instructions

Use the `summarize-video` skill to fulfill this request:

1. **Parse the URL** from `$ARGUMENTS`. If no URL is provided, ask: "Please provide a YouTube URL."
2. **Follow the `summarize-video` skill** step by step:
   - Fetch video metadata
   - Fetch full timed transcript (handle pagination)
   - Detect language
   - Segment into chapters
   - Compose markdown document using `references/output-template.md`
   - Save to `.claude/output/sumYT/`
   - Enter follow-up mode

## Requirements

Node.js and `npx` must be available (standard with any Node.js installation).
The MCP package installs automatically on first use via `npx -y`.
