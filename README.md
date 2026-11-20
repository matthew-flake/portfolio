# Portfolio 2026

Selected image work by **Matthew Flake**. Every image here, and every page of the layout, was generated in **ComfyUI** on a single local machine with an 8 GB GPU. No cloud GPU and no external design tools were used. The page layout is a ComfyUI workflow too, built only from core nodes.

📄 **[Download the PDF](matthew-flake-portfolio-2026.pdf)** (15 pages, 1920 × 1080)

![Cover](pages/01_cover.png)

## Projects

### 01 · Stylised character pipeline
I designed one original character from a text brief and generated a three-view turnaround sheet. Each later scene uses that sheet as a reference latent, so the face, outfit and proportions stay consistent.

![Character sheet](pages/02_character_sheet.png)
![Character scenes](pages/03_character_scenes.png)

### 02 · Sketch to render: single-family house
A concept sketch is used as the reference for a photoreal day render and a blue-hour variant. The massing, roof pitch and facade carry over from the sketch.

![Arch viz](pages/04_arch_viz.png)

### 03 · One product, three campaign looks
An original product (a ceramic aroma diffuser) is generated once as a packshot and then restaged in three settings. Its shape, materials and details are kept.

![Product](pages/05_product.png)

### 04 · Game art: vehicles and naval key art
Original vehicle designs with no insignia. The cinematic key art is the reference for every view on the design sheet: the side, three-quarter and front views are generated one at a time from it and composited in the same graph, with a turret close-up cropped from the side view.

![Vehicles](pages/06_game_vehicles.png)

### 05 · Casual mobile: room scene and icon set
An isometric room in a casual mobile style and a set of nine item icons generated in one consistent look.

![Casual mobile](pages/07_game_casual.png)

### 06 · Anime character with three skins
An original cel-shaded character turnaround, then three skins generated from it as a reference latent. Face and hair stay the same, while the outfit and setting change.

![Character turnaround](pages/08_game_character.png)
![Character skins](pages/09_game_skins.png)

### 07 · Key art, environments and expressions
A sci-fi desert environment concept, a key art image for a mobile fishing game and one casual character in four expressions.

![Key art and environments](pages/10_game_keyart.png)

### 08 · Vehicle skins and UI icons
Three camouflage skins of the same tank. The side view is cropped from the design sheet inside the graph and used as the reference, so only the paint changes. Two item icon sets: vehicle consumables and sci-fi battle royale loot.

![Vehicle skins and icons](pages/11_game_vehicle_skins.png)

### 09 · Casual makeover: before and after
The finished room from project 05 is the reference for its run-down "before" state, so both frames share the same isometric view, walls and furniture layout.

![Makeover](pages/12_game_makeover.png)

### 10 · Fishing key art in two styles
A semi-realistic render with a recognisable northern pike next to the stylised casual version from project 07.

![Fishing styles](pages/13_game_fishing_styles.png)

### 11 · Process: from sheet to skin
The real first pass of the three skins from project 06 next to the final versions, with the reason each first version was rejected.

![Process](pages/14_process_sheet_to_skin.png)

### 12 · Setup & method
![Setup and method](pages/15_setup_method.png)

## What's in this repo

| Folder | Contents |
|---|---|
| [`images/`](images) | The 34 source images, full resolution, including the three rejected first versions shown on the process page. Each PNG carries its own workflow, so you can drag it into ComfyUI. |
| [`workflows/images/`](workflows/images) | One API-format workflow per image (prompt, seed, sampler settings) |
| [`workflows/pages/`](workflows/pages) | The page-layout workflows (EmptyImage, LoadImage, ImageScale, TextOverlay, ImageCompositeMasked) |
| [`pages/`](pages) | The fifteen finished pages |
| [`TESTED.md`](TESTED.md) | Hardware, software and measured timings |
| [`MODELS.md`](MODELS.md) | Model files, where to get them, licences |

## Reproducing

1. Download the models listed in [MODELS.md](MODELS.md) into the usual ComfyUI model folders.
2. Workflows that load an image (reference scenes and page layouts) expect the files from `images/` in `ComfyUI/input/`. Copy them there first.
3. Load a JSON from `workflows/` with *Workflow → Open*, or drag the matching PNG onto the canvas, then queue it. Where I generated a batch of candidates, the workflow ends with `ImageFromBatch` set to the image I picked.

Seeds are fixed, but results can still differ slightly between GPUs, drivers and ComfyUI versions.

## Books

I write about ComfyUI under this pen name. The companion workflow packs are public:

- [**node-by-node**](https://github.com/matthew-flake/node-by-node): *Node by Node. ComfyUI from Your First Image to Your Own Workflow*
- [**from-noise-to-income**](https://github.com/matthew-flake/from-noise-to-income): *From Noise to Income: The ComfyUI Handbook*

## Licence

- Workflow JSON files: [MIT](LICENSE)
- Images, pages and PDF: [CC BY-NC 4.0](LICENSE-IMAGES.md)

The characters, vehicles, house and product are original designs made for this collection. None of them is based on an existing game, brand or franchise.
