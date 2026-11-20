# Models

Put the files in the standard ComfyUI folders. The names below are the ones used in the workflows; if your copies are named differently, change the loader nodes to match.

## Z-Image-Turbo (images 01–03, 13, 14, 16)

| File | Folder | Source | Licence |
|---|---|---|---|
| `z-image-turbo-fp8-e4m3fn.safetensors` | `models/diffusion_models` | fp8 conversion of [Tongyi-MAI/Z-Image-Turbo](https://huggingface.co/Tongyi-MAI/Z-Image-Turbo). The bf16 file `z_image_turbo_bf16.safetensors` from [Comfy-Org/z_image_turbo](https://huggingface.co/Comfy-Org/z_image_turbo) works too, but needs more VRAM. | Apache 2.0 |
| `qwen_3_4b.safetensors` | `models/text_encoders` | [Comfy-Org/z_image_turbo](https://huggingface.co/Comfy-Org/z_image_turbo) | Apache 2.0 |
| `ae.safetensors` | `models/vae` | [Comfy-Org/z_image_turbo](https://huggingface.co/Comfy-Org/z_image_turbo) | Apache 2.0 |

Settings: `CLIPLoader` type `lumina2`, `ModelSamplingAuraFlow` shift 3, `KSampler` 8 steps, cfg 1, `res_multistep` / `simple`.

## FLUX.2 [klein] 4B (images 04–12, 15, 17–24)

| File | Folder | Source | Licence |
|---|---|---|---|
| `flux-2-klein-4b-fp8.safetensors` | `models/diffusion_models` | [Black Forest Labs: FLUX.2 [klein]](https://bfl.ai/models/flux-2-klein), 4B distilled model, fp8 | Apache 2.0 (the 9B models use a different, non-commercial licence) |
| `qwen_3_4b.safetensors` | `models/text_encoders` | Qwen3-4B text encoder for FLUX.2 [klein] 4B | Apache 2.0 |
| `flux2-vae.safetensors` | `models/vae` | FLUX.2 VAE | see the Black Forest Labs model card |

Settings: `CLIPLoader` type `flux2`, `Flux2Scheduler` 4 steps, `CFGGuider` cfg 1, `euler`. Reference images go through `ImageScaleToTotalPixels` (1 MP) → `VAEEncode` → `ReferenceLatent`.

## Page layout

The page layout uses no models, only core nodes: `EmptyImage`, `LoadImage`, `ImageScale`, `TextOverlay`, `ImageCompositeMasked`, `SaveImage`.

Check the current licence on each model card before any commercial use. Licences can change, and this table is not legal advice.
