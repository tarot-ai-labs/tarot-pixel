# Quick start

[简体中文](../quick-start.md) · **English**

[Home](../../README.en.md) · [Installation](installation.md) · [Troubleshooting](faq.md)

Goal: sync a small component, ask your agent to implement it in your project, and complete one visual check.

## 1. Prepare your environment

- A coding agent client that supports stdio MCP. Qoder can also use the Tarot Pixel plugin.
- Node.js 20.19.0 or later.
- Chrome, Chromium, Edge, or Brave installed locally for screenshots and composites.
- A card, button group, or another small module in Figma or Sketch.

## 2. Connect Tarot Pixel

Install and enable Tarot Pixel from the [Qoder marketplace](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel). If you use another MCP client or prefer a direct MCP connection, add this server:

```json
{
  "mcpServers": {
    "tarot-pixel": {
      "type": "stdio",
      "command": "npx",
      "args": ["--yes", "--package=@tarot-ai/pixel@latest", "--", "tarot-pixel"]
    }
  }
}
```

The example uses the latest npm release. The first launch requires access to npm. Your client starts and manages the runtime, so you do not need to run another copy in a terminal. If you already have MCP servers configured, merge only the `tarot-pixel` entry. Configuration locations and supported fields vary by client; see [installation](installation.md).

Ask your agent to check the connection:

```text
Call Tarot Pixel's server_status and confirm that the local View is ready.
Then call design_list to list available designs.
An empty list is normal before the first sync.
```

The `view.ready` field in `server_status` should be `true`. If the connection or View is unavailable, follow the [FAQ](faq.md) before continuing.

## 3. Sync a design

1. Install the [Figma plugin](https://www.figma.com/community/plugin/1635645029043726171) or [Sketch plugin](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip).
2. Select the target frame, artboard, or layers in your design tool and open Tarot Pixel.
3. Choose **Sync design** and wait for it to finish.
4. Open or copy the complete local link returned by the plugin. Confirm that the expected module and layers appear in the View.

The design tool and runtime should run on the same machine. Links typically look like `http://127.0.0.1:18276/design/<designId>`; use the actual address returned by the sync.

## 4. Implement it in your project

Open the frontend project you want to modify. Send your agent this prompt, replacing the link and component name:

```text
Use Tarot Pixel to implement this design: <complete synced design link>.
The target is the "Product card" module.

Read the project first and reuse its components, styling conventions, and asset directories.
Locate the module through the design overview, then query the relevant layout, styles, and images.
Keep the title, price, and button dynamic. Use composites for complex decoration where appropriate.
Save generated assets into the project's managed asset directory before referencing them in code.
Run the project, preview at the relevant viewport, compare with the design, and correct major differences.
```

## 5. Make one correction

Point out an observed difference and ask the agent to check the corresponding design data:

```text
The gap between the button and price is too large, and the card background corners differ.
Query the relevant node layout and styles, correct the implementation, and preview it again.
```

You are done when the correct design is visible in the View, the agent can read the target module, the component runs in your project, its assets are saved in the project, and you have compared the rendered result with the design.

Next: [Workflow and prompts](workflow.md).
