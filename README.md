# Portfolio 2026

Selected image work by **Matthew Flake**. Every image here, and every page of the layout, was generated in **ComfyUI** on a single local machine with an 8 GB GPU. No cloud GPU and no external design tools were used. The page layout is a ComfyUI workflow too, built only from core nodes.

📄 **[Download the PDF](matthew-flake-portfolio-2026.pdf)** (6 pages, 1920 × 1080)

![Cover](pages/01_cover.png)

## Projects

### 01 · Stylised character pipeline
I designed one original character from a text brief and generated a three-view turnaround sheet. Each later scene uses that sheet as a reference latent, so the face, outfit and proportions stay consistent.

![Character sheet](pages/02_character_sheet.png)
![Character scenes](pages/03_character_scenes.png)

### 02 · Sketch to render: house with rooftop PV
A concept sketch is used as the reference for a photoreal day render and a blue-hour variant. The geometry, roof pitch and solar array layout carry over from the sketch.

![Arch viz](pages/04_arch_viz.png)

### 03 · One product, three campaign looks
An original product (a ceramic aroma diffuser) is generated once as a packshot and then restaged in three settings. Its shape, materials and details are kept.

![Product](pages/05_product.png)

### 04 · Setup & method
![Setup and method](pages/06_setup_method.png)

## What's in this repo

| Folder | Contents |
|---|---|
| [`images/`](images) | The 12 source images, full resolution. Each PNG carries its own workflow, so you can drag it into ComfyUI. |
| [`workflows/images/`](workflows/images) | One API-format workflow per image (prompt, seed, sampler settings) |
| [`workflows/pages/`](workflows/pages) | The page-layout workflows (EmptyImage, LoadImage, ImageScale, TextOverlay, ImageCompositeMasked) |
| [`pages/`](pages) | The six finished pages |
| [`TESTED.md`](TESTED.md) | Hardware, software and measured timings |
| [`MODELS.md`](MODELS.md) | Model files, where to get them, licences |

## Reproducing

1. Download the models listed in [MODELS.md](MODELS.md) into the usual ComfyUI model folders.
2. Workflows that load an image (reference scenes and page layouts) expect the files from `images/` in `ComfyUI/input/`. Copy them there first.
3. Load a JSON from `workflows/` with *Workflow → Open*, or drag the matching PNG onto the canvas, then queue it.

Seeds are fixed, but results can still differ slightly between GPUs, drivers and ComfyUI versions.

## Books

I write about ComfyUI under this pen name. The companion workflow packs are public:

- [**node-by-node**](https://github.com/matthew-flake/node-by-node): *Node by Node. ComfyUI from Your First Image to Your Own Workflow*
- [**from-noise-to-income**](https://github.com/matthew-flake/from-noise-to-income): *From Noise to Income: The ComfyUI Handbook*

## Licence

- Workflow JSON files: [MIT](LICENSE)
- Images, pages and PDF: [CC BY-NC 4.0](LICENSE-IMAGES.md)

The character, the house and the product are original designs made for this collection.
