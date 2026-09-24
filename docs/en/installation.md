# Installation and connection

[简体中文](../installation.md) · **English**

[Home](../../README.en.md) · [Quick start](quick-start.md) · [Supported capabilities](compatibility.md)

## Requirements

| Component         | Requirement                                                                       |
| ----------------- | --------------------------------------------------------------------------------- |
| Node.js           | 20.19.0 or later; `node` and `npx` must be available to the client process        |
| Coding agent      | stdio MCP support; the Qoder plugin also requires plugin support                  |
| Network           | The first npm runtime launch requires access to the public npm registry           |
| Rendering browser | Chrome, Chromium, Edge, or Brave installed locally for screenshots and composites |
| Design tool       | Figma or Sketch                                                                   |

## Qoder plugin

The Qoder plugin includes MCP configuration and a Skill that guides the agent in using design data.

1. Open [Tarot Pixel in the Qoder marketplace](https://qoder.com/zh/marketplace/plugin?id=tarot-pixel) and follow the installation instructions on the page.
2. Confirm that Tarot Pixel is enabled in Qoder.
3. Start a new task and ask the agent to call `server_status` to verify the connection.

You can also search for `Tarot Pixel` in Qoder's plugin marketplace. For another MCP client, configure the public npm runtime as described below. See [Qoder's plugin documentation](https://docs.qoder.com/qoder/plugins) for its interface instructions.

## Configure MCP directly

Add this entry through your compatible client's custom MCP configuration:

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

- `latest` uses the current npm release. Teams that need a fixed environment can choose a verified version from the [package release information](https://www.npmjs.com/package/@tarot-ai/pixel).
- If `mcpServers` already exists, add only the `tarot-pixel` entry and keep your other servers.
- Some clients accept a single server object. Adapt the configuration to that client's format.
- If the Qoder plugin already starts the runtime, you do not need a second MCP entry for the same service.
- Direct MCP configuration provides the tools. Use the [workflow prompts](workflow.md) to guide queries and implementation.

For Qoder's custom MCP interface, see its [Connectors documentation](https://docs.qoder.com/qoder/connectors).

## Figma plugin

1. Open [Tarot Pixel in Figma Community](https://www.figma.com/community/plugin/1635645029043726171), or search for `Tarot Pixel` in Figma's plugin search.
2. Open your design file and select the frames or layers to sync.
3. Confirm that your client has started the local runtime, run the plugin, and choose **Sync design**.
4. Open the returned local link and check that the design appears in the View.

## Sketch plugin

Requires Sketch 80.0 or later.

1. [Download the plugin ZIP](https://unpkg.com/@tarot-ai/tarot-pixel-sketch-release@latest/Tarot-Pixel.sketchplugin.zip) and extract it.
2. Double-click the extracted `.sketchplugin` to install it.
3. Open your document, select the artboards or layers, and run Tarot Pixel.
4. Confirm that the local runtime is running, then choose **Sync design**. The installed plugin checks for subsequent updates.

The Sketch plugin and runtime are versioned independently. When reporting an issue, include both versions if you know them.

## Verify the connection

Ask your agent to call `server_status` and `design_list`. Once the connection is available and `view.ready` is `true`, sync from your design tool. If `npx` works in your terminal but your desktop client cannot find it, check the client's launch environment or set `command` to the executable's actual path.

If something goes wrong, see the [FAQ](faq.md) or [report an issue](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.en.yml).
