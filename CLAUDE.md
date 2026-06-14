# Unity

Public sandbox for agent-assisted Unity workflows, started from Unity's Setup Guide In-Editor Tutorial project. Used to test Unity MCP and Codex/Claude scene-inspection workflows.

## Stack

- Unity `6000.4.11f1` (Unity 6, macOS Apple Silicon)
- Main scene: `Assets/Scenes/GetStarted_Scene.unity`
- Unity MCP via `com.unity.ai.assistant` (CoplayDev `unity-mcp` as fallback)

## Build / test

No CLI build or test harness — the Unity Editor compiles the project on open. Commit only source state (`Assets/`, `Packages/`, `ProjectSettings/`, repo docs); never `Library/`, `Temp/`, `Logs/`, `UserSettings/`, or builds. See `AGENTS.md` and `README.md` for MCP setup and repo hygiene.

## Knowledge Surfaces

Cross-repo conventions, rules of engagement, and the sibling-repo map live in **Zion** (`~/CC/Zion/CLAUDE.md`) — the canonical workspace index. This repo is a leaf; consult Zion first for workspace-wide protocol.
