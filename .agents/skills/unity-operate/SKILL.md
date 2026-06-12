---
name: unity-operate
description: Use when operating this Unity repo through Unity MCP or local Unity project files.
---

# Unity Operate

Start with public-safe, read-only orientation:

1. Read `AGENTS.md`.
2. Check `ProjectSettings/ProjectVersion.txt`.
3. Check `Packages/manifest.json` and `Packages/packages-lock.json`.
4. If MCP is available, read the Unity console and scene hierarchy before editing.

## Safety Rules

- Do not commit `Library/`, `Temp/`, `Logs/`, `UserSettings/`, builds, captures, or private files.
- Keep write tests under `Assets/MCP_Sandbox/`.
- Do not modify existing scenes unless Mike explicitly asks.
- Do not use Unity account, cloud, package publishing, or build-upload features without explicit approval.

## Useful Checks

```bash
git status -sb
git diff --stat
find . -type f -size +90M -not -path './Library/*' -not -path './Temp/*' -not -path './Logs/*'
```

If Unity MCP is connected, run read-only checks first:

- list Unity MCP tools
- read console
- inspect current scene hierarchy
- list scenes/assets/packages
