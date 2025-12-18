# Javascript-FacadeTransformer

A browser-based Transformer (GPT-2) implementation in JavaScript, featuring a full facade API for inspection, modification, and educational exploration. This system lets you load GGUF model weights and a tokenizer, run autoregressive text generation fully in-browser, and interactively probe every internal aspect of the transformer via the Facade API.

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Getting Started](#getting-started)
- [Basic Example](#basic-example)
- [Facade API](#facade-api)
- [Usage Notes](#usage-notes)
- [License](#license)

---

## About

Javascript-FacadeTransformer is an interactive web application for exploring, running, and probing transformer models directly in your browser.  
Models such as GPT-2 (in open GGUF format) run entirely client-side—no server, no Python.  
A rich Facade API exposes every layer, attention head, and tensor for on-the-fly investigation, visualization, and editing.

Typical use cases include:
- Technical demonstration of transformer internals (multi-head attention, feedforward, embeddings, layer norm, sampling)
- Educational experiments and ablations on text generation
- Deep-dive inspection of model weights, logits, hidden states, attention maps, and more

---

## Features

- **Fully client-side transformer (GPT-2) in JavaScript**  
  - No server, Python, or WebAssembly required
- **Interactive model loading**  
  - Accepts GGUF model files (`.gguf`) and compatible `tokenizer.json` files
- **Text generation**  
  - Native greedy and temperature-based auto-regressive generation from your prompt
- **Introspect and modify all transformer internals via Facade API:**
  - Token/position embeddings, Q/K/V weights per head/layer
  - Intermediate activations, residual pathways, hidden states
  - Attention weights, entropy, and inspection of attention matrices
  - Output logits, softmax probabilities, sampling controls
  - Inspection and editing of layer norms, FFN weights, and more
  - Extraction/visualization of model statistics (histograms, saliency maps)
  - Structural info: layer count, head count, vocabulary size, etc.
- User-friendly web UI to drive all features—no code required
- Output, model summary, and diagnostics appear live in browser

---

## Getting Started

### Requirements

- A modern web browser (Chrome, Firefox, Edge, Safari, etc.)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/matthewJamesAbbott/Javascript-FacadeTransformer.git
    ```
2. Open `index.html` in your browser.

_No build step or server is required._

---

## Basic Example

Run in-browser text generation from a GGUF GPT-2 model:

1. Open `index.html`
2. In **Step 1: Load GGUF Model File**, upload a `GPT-2-*.gguf` file  
   (see [repo](https://github.com/ggerganov/ggml) for conversion tools)
3. In **Step 2: Load Tokenizer**, upload the matching `tokenizer.json`
4. In **Step 3: Generate Text!**:
    - Enter a prompt (e.g. `Once upon a time`)
    - Set max tokens/temperature as desired
    - Click **Generate Text!**
    - View output in the browser
5. Explore the **Facade API Explorer** section to:
    - Inspect embeddings, attention heads, activations, weights, logits
    - Probe/modify per-layer tensors, attention, and model config in real time

---

## Facade API

The Facade API enables you to:

- Get or edit any parameter or intermediate value—token/position embeddings, Q/K/V matrices, attention outputs, FFN (MLP) weights, layer norms, logits, and more
- Step through hidden state transformations for a given prompt
- Visualize and examine the full attention matrix, compute entropy, extract softmax distributions
- Run a forward pass with custom token sequences, layer/head/pos selections
- Gather model summary, vocabulary, top-k logits/probabilities for any state
- Histograms and saliency map tools to analyze feature distributions and model focus
- Modify and reload model or tokenizer files on demand

All controls are available from the web UI.  
Facade outputs and visualizations are displayed directly in the browser, no code required.

---

## Usage Notes

- Designed for moderate GPT-2 models suitable for browser memory and CPU—(for larger models, adjust max tokens or sequence length)
- GGUF files can be created from HuggingFace GPT-2 using conversion tools (see [GGML repo](https://github.com/ggerganov/ggml))
- No external dependencies or backend required; all calculations via JavaScript
- Advanced introspection and mutation is available for research, ablation, and instructional demos

---

## License

MIT License.  
Open for use, modification, and distribution in any educational, research, or technical setting.

---

## Vercel Link

https://javascript-facade-transformer.vercel.app/
