# Bridging the Training Gap with Hyperion

**A Training-Free Style Transfer Method on Diffusion Transformers**

> TPAMI submission · v1.5 · 2026-07-09

## Authors

Yi Li, Chengyan Li, Zhirui Fang, Junchuan Zhang, Yan Luo, Yanqing Guo (Dalian University of Technology) · Xuan Wang (Beihang University) · Huaibo Huang (Institute of Automation, Chinese Academy of Sciences)

## Abstract

Training-free style transfer on Multimodal Diffusion Transformers (MM-DiT) remains challenging due to the persistent gap between trained adapters and injection-based training-free methods. Existing training-free methods typically perform forward feature injection, and thus struggle to reproduce the rich painterly textures achieved by trained adapters, often leading to only faint hue shifts.

We propose **Hyperion**, a fully training-free style-transfer pipeline for MM-DiT built on two components:

- **Adam-in-loop** — iteratively optimizes the diffusion latent at each denoising step with a frozen MM-DiT, recovering the gradient-driven spatial coupling (via the self-attention value path) that produces coherent brushstroke textures.
- **Sinkhorn Latent Transport (SLT)** — a single closed-form optimal-transport step that pre-aligns latent color distributions before Adam optimization, improving operational efficiency.

Hyperion achieves **CLIP-T 0.296** on the full 234-pair benchmark, outperforming the equal-budget Adam-only baseline by **+16.6%** and the best prior training-free method by **+5.2%**, ranking 19/21 methods overall (mean style score 0.657 vs. 0.506 for the runner-up).

## Repository Contents

| File | Description |
|------|-------------|
| `main.pdf` | Manuscript for review (18 pp, body + references) |
| `supplementary.pdf` | Supplementary material (21 pp, appendices A–L) |
| `main.tex` | Root LaTeX source (IEEEtran 10pt journal compsoc) |
| `sec/` | Paper sections and appendices |
| `bib/refs.bib` | Bibliography |
| `fig/` | 31 figures (18 vector PDFs + 13 JPEG galleries) |
| `figures_hires/` | Full-resolution figure masters |

## Build

```bash
pdflatex main && bibtex main && pdflatex main && pdflatex main
```

Requires a standard TeX Live distribution with `IEEEtran.cls` / `IEEEtran.bst`.

The source compiles as one 39-page document; `main.pdf` (pages 1–18) and `supplementary.pdf` (pages 19–39) are split from the combined output.

## Notes

- All quantitative results use fixed seed 43 (see paper Sec. 4).
- Headline CLIP-T is 0.296, re-measured on a separate 8×H100 run.
