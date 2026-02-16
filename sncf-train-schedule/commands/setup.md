---
description: Configure SNCF plugin with your Navitia API token (persists across plugin updates)
argument-hint: "[your-navitia-api-token]"
allowed-tools: ["Write", "Bash", "Read"]
---

# /setup - SNCF Plugin Setup

Saves the Navitia API token to `.claude/sncf-train-schedule.local.md` in the current project. This file is gitignored and survives plugin updates.

## Instructions

1. **Get the token**:
   - If `$ARGUMENTS` is non-empty, use it as the token
   - Otherwise check `NAVITIA_API_TOKEN` env var: `echo $NAVITIA_API_TOKEN`
   - If neither is set, ask the user to provide their token (free registration at https://numerique.sncf.com/startup/api/token-developpeur/)

2. **Create the settings file**:
   ```bash
   mkdir -p .claude
   ```
   Then write `.claude/sncf-train-schedule.local.md` with this exact content:
   ```
   ---
   navitia_api_token: <token>
   ---
   ```

3. **Confirm setup** — tell the user:
   - Token saved to `.claude/sncf-train-schedule.local.md`
   - File is gitignored — will not be committed
   - Token persists across plugin updates
   - All scripts and hooks will pick it up automatically

## Notes

- This file takes precedence over `.env` but not over `NAVITIA_API_TOKEN` env var
- To update the token, run `/setup` again or edit `.claude/sncf-train-schedule.local.md` directly
- To remove it: `rm .claude/sncf-train-schedule.local.md`
