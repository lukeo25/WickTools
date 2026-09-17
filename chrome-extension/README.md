# LukeTools Chrome Extension

This folder contains an unpacked Chrome extension version of LukeTools.

## What it does

The extension automatically injects the existing Luke Tools Local Panel Bridge into Wick Editor.

It preserves the current LukeTools architecture:

Chrome Extension -> LukeTools Bridge -> Config.json -> individual LukeTools scripts -> Wick Editor

The bridge source in `luketools-bridge.js` is extracted directly from the current `LukeTools.wickobj` file in this repository.

## Install in Chrome

1. Download or clone the `chrome-extension` branch.
2. Open `chrome://extensions`.
3. Turn on **Developer mode**.
4. Click **Load unpacked**.
5. Select the `chrome-extension` folder.
6. Open `https://www.wickeditor.com/editor/`.
7. LukeTools should load automatically.

## Updating during development

After changing extension files, click **Reload** for LukeTools on `chrome://extensions`, then refresh Wick Editor.

## Architecture

The bridge is packaged locally in the extension. Your existing `Config.json`, icon URLs, script URLs and tool URLs remain unchanged, so the extension continues to use the current modular LukeTools setup.

The working `main` branch has not been changed.
