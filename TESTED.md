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
| Page layout, first 6 pages | core image nodes, no model | – | 6 | 1.8 s | ~0.3 s |
| Game art: vehicle, naval and desert key art | Z-Image-Turbo (fp8) | 8 | 3 | 63.7 s (including model load) | ~16 s |
| Game art: sheets, casual assets, character and skins | FLUX.2 [klein] 4B (fp8) | 4 | 9 | 69.2 s (including model load) | ~7 s |
| Game art: re-renders after review | FLUX.2 [klein] 4B (fp8) | 4 | 5 | 42.0 s | ~8 s |
| Page layout, game pages + setup page | core image nodes, no model | – | 6 | 3.2 s | ~0.5 s |
| Rebuilt vehicle sheet: side, front and 3/4 candidates | FLUX.2 [klein] 4B (fp8) | 4 | 9 | ~95 s (including model load) | ~8.5 s |
| Camouflage skins, icon sets, room "before" | FLUX.2 [klein] 4B (fp8) | 4 | batches of 3 | ~25 s per batch | ~8 s |
| Semi-realistic fishing key art | Z-Image-Turbo (fp8) | 8 | 3 | – | ~16 s |
| Page layout, five new and one updated page | core image nodes, no model | – | 6 | under 8 s for all six | – |

## Notes

- Both diffusion models use fp8 weights so they fit in 8 GB of VRAM. Between the Z-Image and FLUX.2 jobs I freed memory with ComfyUI's `/free` endpoint so the two models were never loaded at the same time.
- Resolutions were kept around 1 MP (for example 1536 × 864, 1344 × 768, 864 × 1152, 1216 × 832).
- I review every image by eye. Two outputs from the first set were rejected and regenerated. In one, the product looked too close to an existing commercial design. In the other, the neon signs came out as garbled text, so the new prompt asks for abstract neon shapes and no lettering.
- In the game set, five images were regenerated after review: the vehicle sheet showed six near-identical side views instead of three distinct views, the icon set repeated one item, two skins had pseudo-lettering on signs, and two skins lost the character's hair colour or face. The new prompts ask for exactly three views, list each icon once, and ask for no signs and a visible face and hair. The first versions of the three skins are kept in `images/32–34` and shown on the process page.
- The second vehicle sheet still showed three slightly different tanks (different turrets and wheel counts). I rebuilt it: each view is now generated separately from the key art, I picked the candidates that match (five road wheels, tall cupola, muzzle brake, drum on the rear deck), and the views are composited in the same graph. The camouflage skins use the side view from that sheet as their reference.
- Rejected in the new set: icon and fishing candidates that contained lettering, a woodland skin with a fake signature in the corner, and skins whose wheel count or turret did not match the sheet.
- With both models cached, one batch failed with an out-of-memory error in system RAM. Calling `/free` before the next batch fixed it.
- `TextOverlay` sets `font_size` as a percentage of the strip height, with a maximum of 50%. The page workflows size each text strip to stay within that limit.
