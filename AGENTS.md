# AGENTS.md - Unity

This is a public Unity workspace for agent-assisted Unity experiments.

## Working Rules

- Keep the repository public-safe. Do not commit private notes, screenshots, recordings, credentials,
  Unity account data, or local machine caches.
- Commit only Unity source project state: `Assets/`, `Packages/`, `ProjectSettings/`, and small repo
  docs/configuration.
- Never commit `Library/`, `Temp/`, `Logs/`, `UserSettings/`, builds, captures, or exported binary
  deliverables unless Mike explicitly asks for a release artifact.
- Prefer read-only MCP checks before writes: read console, list tools, inspect scene hierarchy, and
  list packages/assets.
- For write tests, create an isolated scratch scene under `Assets/MCP_Sandbox/` and avoid touching
  existing scenes unless Mike asks.
- Treat generated scripts and package changes as code changes: inspect diffs and verify Unity can
  compile before publishing follow-up commits.

## Unity MCP Setup

The intended first path is official Unity MCP through `com.unity.ai.assistant` on Unity 6+.

After Unity resolves packages, check:

```text
Edit > Project Settings > AI > Unity MCP
```

The expected macOS Apple Silicon relay path is:

```text
~/.unity/relay/relay_mac_arm64.app/Contents/MacOS/relay_mac_arm64
```

Codex MCP config:

```toml
[mcp_servers.unity-mcp]
enabled = true
command = "/Users/mikeedwards/.unity/relay/relay_mac_arm64.app/Contents/MacOS/relay_mac_arm64"
args = ["--mcp"]
```

If the official package is unavailable or blocked, use CoplayDev's Unity MCP package as the fallback:

```text
https://github.com/CoplayDev/unity-mcp.git?path=/MCPForUnity#main
```

## Verification

Before claiming Unity MCP is working:

1. Confirm the relay executable exists.
2. Confirm Unity shows the bridge running.
3. Confirm the MCP client lists Unity tools.
4. Run read-only checks only: console summary and scene hierarchy.

For normal git hygiene:

```bash
git status -sb
git diff --stat
```
