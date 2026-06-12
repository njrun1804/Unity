# Unity

Public Unity workspace for exploring agent-assisted Unity workflows.

This repo currently starts from Unity's **Setup Guide In-Editor Tutorial** project and is intended
as a safe place to test Unity MCP, Codex/Claude workflows, scene inspection, small sandbox changes,
and project-specific agent tooling.

## Project

- Unity version: `6000.4.11f1`
- Main scene: `Assets/Scenes/GetStarted_Scene.unity`
- Official Unity MCP path: `com.unity.ai.assistant`

## Unity MCP

The official Unity MCP flow requires Unity 6+ and the `com.unity.ai.assistant` package. After the
project opens and packages resolve, Unity should expose:

```text
Edit > Project Settings > AI > Unity MCP
```

The relay should be installed under:

```text
~/.unity/relay/relay_mac_arm64.app/Contents/MacOS/relay_mac_arm64
```

Codex can then be configured with:

```toml
[mcp_servers.unity-mcp]
enabled = true
command = "/Users/mikeedwards/.unity/relay/relay_mac_arm64.app/Contents/MacOS/relay_mac_arm64"
args = ["--mcp"]
```

Start with read-only checks: read the Unity console, list tools, inspect the active scene hierarchy,
and list packages/assets. Use a scratch scene for any write test.

## Repo Hygiene

Commit Unity source project state only:

- `Assets/`
- `Packages/`
- `ProjectSettings/`
- repo docs and agent instructions

Do not commit Unity generated state such as `Library/`, `Temp/`, `Logs/`, `UserSettings/`, builds,
recordings, captures, or private notes.
