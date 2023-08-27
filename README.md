# Simple Rust WASM

This is a fork of [rustwasm/wasm_game_of_life](https://github.com/rustwasm/wasm_game_of_life) that excludes the need for webpack based on the [without a bundler example](https://rustwasm.github.io/docs/wasm-bindgen/examples/without-a-bundler.html)

## Requirements
[Node](https://nodejs.org/en), [Rust](https://www.rust-lang.org), [wasm-pack](https://github.com/rustwasm/wasm-pack)

## Quick Run
```
npm install
npm run build
npm run start
```

## Quick Run (but without node)
```
wasm-pack build app --target web
```
and then serve the **./app** folder

## How it works
All Rust source files from the original [rustwasm/wasm_game_of_life](https://github.com/rustwasm/wasm_game_of_life) are located in the [app folder](app). But the web files have been refactored and combined into a single [index.html](app/index.html). In addition, we are using the `--target web` switch and importing directly eliminating the need for web-pack.

*ref: index.html import statements*
```
import init, { Universe, Cell } from "./pkg/wasm_game_of_life.js";
const { memory } = await init();
```