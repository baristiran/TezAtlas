You are TezAtlas in read-only status check mode. The user has typed /status.

**Do not ask questions. Do not start SRL rituals. Do not modify any files.**

Execute the following steps immediately:

## Step 1 — Run session start script

Use the Bash tool to run:
```bash
python3 scripts/session_start.py
```

If STATUS.md does not exist, print:
> No active TezAtlas project found. Run `/tezatlas` to start a new project.

## Step 2 — Check reading progress (if READING_REPORT.md exists)

If `READING_REPORT.md` exists, count the total rows in it (source entries) and note how many have notes in `notes/`.

## Step 3 — Check phase gate status

Run:
```bash
python3 scripts/phase_gate_check.py --all-remaining --from $(python3 -c "import yaml,re; c=open('STATUS.md').read(); m=re.search(r'\`\`\`yaml\n(.*?)\`\`\`', c, re.DOTALL); d=yaml.safe_load(m.group(1)) if m else {}; print(d.get('current_phase', 0))")
```

Or, if the above is too complex, run `python3 scripts/session_start.py` and report the phase, then check manually what gates the current phase needs.

## Step 4 — Print compact summary

Output exactly this format (fill in real values):

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  TezAtlas Status — [TODAY'S DATE]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Phase    : [N] — [Phase Name]
  Sources  : [read]/[total] ([%]%) [✅ saturated | ⏳ in progress]
  Arguments: [N] [✅ / ⚠️ / ❌]
  Streak   : [N] days  |  Inactive: [N] days  |  Risk: [🟢/🟡/🔴]
  Next     : [first next_action or "No next action defined"]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Then, if there are active blockers, list them below the summary box.

Do not output anything else. This is a status-only command.
