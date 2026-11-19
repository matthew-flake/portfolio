# Tested on

Everything in this repository was generated and laid out on the same machine I used for the workflows in both books.

| | |
|---|---|
| CPU | Intel Core i5-14400F |
| RAM | 32 GB |
| GPU | NVIDIA GeForce RTX 5060, 8 GB VRAM |
| OS | Windows 11, 64-bit |
| ComfyUI | 0.39 (portable install), Python 3.12 |
| Custom nodes | none: every workflow here uses core nodes only |

## Measured times

These are wall-clock times reported by ComfyUI for each queued job.

| Job | Model | Steps | Images | Total time | Per image (model already loaded) |
|---|---|---|---|---|---|
| Key visual, sketch, packshot | Z-Image-Turbo (fp8) | 8 | 3 | 58.4 s (including model load) | ~16 s |
| Character sheet, scenes, renders, product looks | FLUX.2 [klein] 4B (fp8) | 4 | 9 | 82.4 s (including model load) | ~9.5 s |
| Re-render of the rain scene | FLUX.2 [klein] 4B (fp8) | 4 | 1 | 9.5 s | ~9.5 s |
| Page layout, all 6 pages | core image nodes, no model | – | 6 | 1.8 s | ~0.3 s |

## Notes

- Both diffusion models use fp8 weights so they fit in 8 GB of VRAM. Between the Z-Image and FLUX.2 jobs I freed memory with ComfyUI's `/free` endpoint so the two models were never loaded at the same time.
- Resolutions were kept around 1 MP (for example 1536 × 864, 1344 × 768, 864 × 1152, 1216 × 832).
- I review every image by eye. Two outputs were rejected and regenerated. In one, the product looked too close to an existing commercial design. In the other, the neon signs came out as garbled text, so the new prompt asks for abstract neon shapes and no lettering.
- `TextOverlay` sets `font_size` as a percentage of the strip height, with a maximum of 50%. The page workflows size each text strip to stay within that limit.
