# prompt-to-page

A local-first prompt-to-page tool. Type a prompt, get one `index.html` with inline CSS, opened in your browser.

Built on [OpenDesign](https://github.com/nexu-io/open-design) (Apache-2.0), with Xiaomi MiMo (`mimo-v2.6-pro`) or local OpenCode models.

It is deliberately smaller than heavyweight SaaS design tools: no cloud, no accounts, no design system to adopt, no collaboration.

**Extras**
- **Design-token extraction:** URL → screenshot → colour, type, spacing and motion tokens.
- **Motion export:** hand the page to HyperFrames and render it to MP4 locally, no GPU needed.

> **Status:** today this runs through OpenDesign plus the bundled `skills/hyperframes-handoff` skill and the `design-systems/manifest-motion` package. The standalone `src/`, `tokens/` and `motion/` modules are on the roadmap.

## Quick start

Requires Node 24.

```bash
git clone https://github.com/nexu-io/open-design.git
cd open-design
npm install -g pnpm@10
pnpm install
pnpm tools-dev run web
```

### Model: MiMo

Add MiMo as a **custom OpenAI-compatible provider**. Don't use the built-in MiMo preset, because it points to the China endpoint.

```text
Base URL: https://token-plan-sgp.xiaomimimo.com/v1
Model:    mimo-v2.6-pro
API key:  your tp- Token Plan key (never commit it)
```

### Model: OpenCode

Install the `opencode` CLI and choose OpenCode as the agent in OpenDesign's settings. Note: small free models may answer without writing any files.

## Example

Prompt ([`examples/example-prompt.txt`](examples/example-prompt.txt)):

```text
Build a single HTML file named index.html for a landing page called Manifest Motion. Dark midnight background, gold headline Design that moves, one sentence of subtext, one Get started button. Inline CSS only, no external files, no JavaScript. Do not write any markdown, readme, or explanation — the only file you create is index.html.
```

Output: a single `index.html` with a dark midnight page, the gold headline "Design that moves", a line of subtext and a "Get started" button.

## Design philosophy

- **One file out.** Every result is a single portable HTML file.
- **Local first.** Your prompts, keys and pages stay on your machine.
- **Fewer features.** Do one job well instead of rebuilding a design suite.
- **Bring your own model.** A hosted API or a local agent, your choice.

## Roadmap

- [ ] `tokens/` module: standalone URL-to-tokens extraction
- [ ] `motion/` bridge: standalone HyperFrames MP4 export
- [ ] Provider failover: MiMo → Grok → Gemini → Claude → OpenAI
- [ ] Local ComfyUI hook for generated images and video

## Contributing

Issues and pull requests are welcome. Keep changes small, local-first and free of new cloud dependencies. Never commit API keys.

## License

Apache-2.0. OpenDesign is also Apache-2.0; see its repository for its own notices.
