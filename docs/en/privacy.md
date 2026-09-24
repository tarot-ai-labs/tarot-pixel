# Data and privacy

[简体中文](../privacy.md) · **English**

[Home](../../README.en.md) · [Support](../../SUPPORT.en.md)

## Local data

The Tarot Pixel local runtime stores design data, assets, and rendering results in the current user's local data directory by default. The full runtime, View, and MCP HTTP service bind to the local loopback address. Design tools sync through a dedicated import channel.

A local runtime does not mean that all data in the AI workflow remains on your machine. Design text, styles, screenshots, or assets read by your coding agent may be sent to the client and model services you use. Choose suitable content according to your design tool, client, model provider, and organization requirements.

## Asset use

Save generated images and fonts into your project's managed asset directories before referencing them. Rights to use designs, fonts, images, and other material are governed by their respective owners' or providers' terms.

## Public feedback

Issues and Discussions in this repository are public. Share only what is needed to investigate the problem:

- Remove customer information, internal project names, and business data from screenshots.
- Remove credentials, tokens, account information, and full local paths from logs.
- Share source design files only when you can make them public; prefer a minimal reproduction.

Opening this repository does not automatically upload your local designs. You submit feedback yourself through GitHub forms.
