# Repository structure

Items marked *(planned)* don't exist yet; today the work runs through OpenDesign.

```text
prompt-to-page/
├── README.md                              # Pitch, quick start and roadmap
├── example-prompt.txt                     # The prompt that produced the Manifest Motion page
├── src/index.js                           # (planned) CLI entry: prompt in, index.html out
├── src/providers.js                       # (planned) MiMo, OpenCode and failover provider setup
├── src/prompt.js                          # (planned) Builds the single-file HTML prompt
├── src/write.js                           # (planned) Writes index.html and opens the browser
├── tokens/extract.js                      # (planned) URL → screenshot → design tokens
├── tokens/tokens.css                      # (planned) Extracted tokens as CSS custom properties
├── tokens/DESIGN.md                       # (planned) Human-readable token summary
├── motion/export.js                       # (planned) HyperFrames handoff and MP4 render bridge
├── skills/hyperframes-handoff/SKILL.md    # Included: OpenDesign skill handing pages to HyperFrames
├── design-systems/manifest-motion/        # Included: Manifest Motion design-token package
├── examples/example-prompt.txt            # Included: sample prompt
├── examples/manifest-motion/index.html    # (planned) Sample output page
├── package.json                           # (planned) Node package manifest
├── .env.example                           # (planned) Placeholder keys, never real ones
└── LICENSE                                # (planned) Apache-2.0 text
```
