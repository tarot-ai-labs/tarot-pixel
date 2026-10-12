# FAQ

[简体中文](../faq.md) · **English**

[Home](../../README.en.md) · [Report an issue](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.en.yml)

## The agent cannot find Tarot Pixel tools

Check that the plugin is enabled and ask the agent to call `server_status` in a new session. For a manual MCP setup, check your Node.js version, network, and whether the client can find `npx`. See [installation](installation.md) for the configuration.

## A design will not sync

Start your client with Tarot Pixel enabled and ask the agent to check `server_status`. Once `view.ready` is `true`, sync the design. Run the design tool and client on the same computer.

## A design or node is missing

Sync from your design tool and open the returned link to confirm the design is present. After changing the design, sync again and give the agent the latest complete link.

## The design link will not open

Keep your client running and use the address returned by the current sync. Check for duplicate Tarot Pixel MCP entries; disable duplicates and restart the client if needed.

## A screenshot or composite fails

Install Chrome, Chromium, Edge, or Brave and confirm the local design preview is ready. Retry with a small module. If it still fails, include the error message when [reporting the issue](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.en.yml).

## Fonts or line breaks differ from the design

Install the design's fonts and check the weight, size, line height, and page width, then preview again.

## Text appears twice over an image

Ask the agent to check which elements are already part of the image and avoid drawing them again. Implement text that needs to change separately in code.

## Images break after deployment

Copy images into your project's asset directory and reference those project paths. Local temporary addresses are for reading and transferring assets.

## Can I send a local design link to a teammate?

The local link works only on your computer. Your teammate needs to sync the design on their own computer.

## How do I implement states and interactions?

Give the agent the designs and business conditions for each state. Describe button actions, data sources, and state transition rules.

## Where is design data stored?

Synced design data and assets are stored on your computer. When the agent calls a model, the design information it reads may be included in the context sent to the model service.
