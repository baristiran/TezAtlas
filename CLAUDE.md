# TezAtlas — CLAUDE.md (Auto-loaded Context)

This file is read by Claude at session start.

## Project

TezAtlas is an Agentic AI Workflow Framework for producing any academic output.
Run `/tezatlas` to begin a new project or resume an existing one.

## Session Recovery

If context is lost, follow these steps:
1. Read `skills/core/onboarding.md` → determine document type and language
2. Read `STATUS.md` (if it exists) → current phase and progress
3. Read `READING_REPORT.md` (if it exists) → source reading progress
4. Check `notes/` folder → completed source notes
5. Run `/tezatlas` to re-initialize if needed

## Iron Rules (always active)

1. No writing without source in local /sources/ folder
2. Snowball sampling mandatory (follow footnotes)
3. AI downloads sources first before asking user
4. No fabricated citations — ever
5. Advisor/supervisor checkpoints before phase transitions
6. Git commit mandatory after every session
7. No progress without action — escalate blockers immediately
8. Defense armor at reading phase exit (strongest support + counter per argument)
9. Deferred source pool reviewed before writing phase

## Operating Modes

**Thought Partner** (default): AI guides, questions, checks. User writes every word.
**Draft Generator**: AI drafts from user notes/sources. User must critically review and own.

Hard rule: AI NEVER generates core thesis, arguments, data interpretation, or conclusions — in either mode.

Student Mode → Thought Partner enforced, Draft Generator unlocks via Mastery Path.
Researcher Mode → both modes available, Thought Partner pre-selected.

## OCR

Automatic: PyMuPDF (text-layer) → Tesseract (scanned fallback)
```
python3 ocr_pipeline.py sources/ --batch --lang tur+eng
```

## MCP Server (Academic APIs)

TezAtlas includes an MCP server that exposes Semantic Scholar, OpenAlex, and CrossRef
as structured tools. To enable it, add to your `claude_desktop_config.json` or `.claude/mcp.json`:

```json
{
  "mcpServers": {
    "tezatlas-academic": {
      "command": "python3",
      "args": ["<absolute-path-to-TezAtlas>/mcp_server/server.py"],
      "env": {
        "S2_API_KEY": "optional-semantic-scholar-key"
      }
    }
  }
}
```

Once connected, the source_hunter agent and find_source.py gain access to richer
semantic search capabilities via the MCP tools.

## Supported Document Types

- Doctoral / Master's Thesis → skills/phases/thesis/
- Journal Article → skills/phases/article/
- Conference Paper → skills/phases/conference/
- Literature Review → skills/phases/lit-review/
- Research Report → skills/phases/report/
- Book Chapter → skills/phases/book-chapter/
- Grant Proposal → skills/phases/grant-proposal/
- Research Proposal / Prospectus → skills/phases/research-proposal/
