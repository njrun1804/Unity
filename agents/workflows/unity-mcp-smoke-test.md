# Unity MCP Smoke Test

Use this after Unity has resolved `com.unity.ai.assistant` and the relay exists.

## Read-Only Checks

1. Confirm the MCP client lists Unity tools.
2. Read the Unity console and summarize warnings/errors.
3. List the current scene hierarchy.
4. List scenes, packages, and top-level asset folders.

Stop here unless Mike asks for a write test.

## Smallest Write Test

1. Create `Assets/MCP_Sandbox/`.
2. Create `Assets/MCP_Sandbox/MCP_SmokeTest.unity`.
3. In that scene only, create:
   - red cube at `(0, 1, 0)`
   - camera
   - directional light
   - material asset for the cube
4. Save the scene.
5. Report the changed files.
