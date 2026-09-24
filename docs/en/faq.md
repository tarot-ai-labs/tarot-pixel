# Frequently asked questions

[简体中文](../faq.md) · **English**

[Home](../../README.en.md) · [Report an issue](https://github.com/tarot-ai-labs/tarot-pixel/issues/new?template=bug-report.en.yml)

## My agent cannot see Tarot Pixel's tools

Confirm that the plugin or MCP server is enabled, then call `server_status` in a new session. For npm configuration, check your Node.js version, network access, and the client's `PATH`. If your client expects a single server object, adapt the configuration accordingly. See [installation](installation.md) for the full example.

## I installed the design tool plugin. Why does sync still fail?

The design tool plugin exports data, while the local runtime receives it. Start the client connected to Tarot Pixel, ask the agent to call `server_status`, and confirm that `view.ready` is `true` before syncing.

## The design list is empty, or a node cannot be found

An empty list is normal before the first sync. After syncing, check that the design appears in the View and copy the actual returned link or identifier. Use node and module identifiers from the current design data. After changing the source design, sync again and ask the agent to read the current overview.

## The View does not open

Use the address returned by the current `server_status` or sync result, and confirm that the runtime is still running. Check for duplicate runtime configurations or port conflicts, then inspect your client's MCP error messages. Disable a duplicate configuration if needed and restart the client; deleting design data is unnecessary.

## Screenshots or composites fail

Confirm that a supported browser is installed and the View is ready in `server_status`. Try a small module first and record the failing steps and error message. If only one design fails, a sanitized minimal example helps distinguish rendering environment problems from layer content problems.

## Fonts, line breaks, or text widths differ from the design

Check whether the required font is installed and verify the weight, size, line height, and viewport. Font substitution affects layout. Before distributing a font subset, check that the font's license permits its use and distribution in your project.

## Text appears both inside an image and again on the page

Some assets already contain text or other visual elements. Ask the agent to inspect the node's image content metadata to see what is baked into the image. If the text needs to be dynamic, decide how to separate the image from editable content.

## Images work locally but break after deployment

Local paths, resource URIs, and temporary URLs returned by the runtime are for reading or copying assets. Copy the assets into your project's managed asset directory and reference project paths. Business code should not depend directly on the local runtime's address.

## How can I share a design link with a teammate?

A local link points to the visitor's own machine, so it cannot serve as a cross-machine sharing link. Your teammate needs to sync the design or obtain usable design data in their own environment. For public feedback, describe the problem and attach a sanitized screenshot or minimal example.

## Can it infer every interaction and component state?

A static design can show how states look, but requirements still need to explain behavior. Tell the agent which conditions activate each state and what each button does. Module differences help with comparison but do not replace business definitions.

## Is a perfect first implementation guaranteed?

No. Design quality, model capabilities, fonts, assets, viewport, and project constraints affect the result. Start with a small module, preview it, and point out specific differences so the agent can revisit the design and refine the implementation.

## Can I report a problem without knowing the version?

Yes. Enter “Not sure” in the form. Screenshots and logs are optional. Explain where the problem occurred, what you expected, and what actually happened; maintainers can help gather further details.
