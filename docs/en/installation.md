# Installation

[简体中文](../installation.md) · **English**

[Home](../../README.en.md) · [Quick start](quick-start.md) · [FAQ](faq.md)

## Requirements

- Node.js 20.19.0 or later, with `node` and `npx` available to your client.
- Qoder or a client that supports stdio MCP.
- Chrome, Chromium, Edge, or Brave for screenshots and composites.
- Figma or Sketch running on the same computer as your client.
- Access to the public npm registry for the first launch.

## Qoder plugin

1. Open the [Tarot Pixel plugin page](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel) and follow the installation steps.
2. Enable Tarot Pixel for your Qoder task.
3. Keep Qoder running and sync a design from your design tool.

## Figma plugin

1. Open Tarot Pixel in [Figma Community](https://www.figma.com/community/plugin/1635645029043726171).
2. Select the target frames or layers and run the plugin.
3. Choose **Sync design** and open the returned link to view the design.

## Sketch plugin

Requires Sketch 80.0 or later.

1. [Download the plugin ZIP](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip) and extract it.
2. Double-click the `.sketchplugin` file to install it.
3. Select artboards or layers, run Tarot Pixel, and choose **Sync design**.

## Configure MCP directly

For another compatible client, add this entry to its MCP configuration:

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

If you already have MCP servers configured, add only the `tarot-pixel` entry. No additional entry is needed when the Qoder plugin is enabled.

[Sync your first design →](quick-start.md) · [Troubleshooting](faq.md)
