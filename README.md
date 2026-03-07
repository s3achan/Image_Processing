# 🖼️ Image Processing with PIL

A hands-on Python project exploring image manipulation, pixel-level operations, and pixel art generation using **Pillow (PIL)**, **NumPy**, and **Matplotlib** — all in Jupyter Notebooks.

---

## 📁 Notebooks

### 1. `Image-Processing-v2.ipynb` — Core Image Operations
A structured walkthrough of fundamental image processing techniques using a real photo (`redbull.jpg`).

| Section | Topic |
|---------|-------|
| 1 | Setup & Load |
| 2 | Save |
| 3 | Crop |
| 4 | Rotate & Flip |
| 5 | Resize |
| 6 | Colour Conversions |
| 7 | Filters |

**Key concepts covered:**
- Loading and inspecting images (`size`, `mode`, `format`)
- Cropping with `(left, upper, right, lower)` box coordinates and understanding pixel coordinate shifts
- Rotating with `expand=True` to prevent clipping; lossless flips via `transpose()`
- Resizing with `Image.LANCZOS` for quality downscaling
- Colour mode conversions: RGB → Greyscale (`L`) → Binary (`1`) using threshold logic
- Applying built-in convolution filters: `BLUR`, `SHARPEN`, `EDGE_ENHANCE`, `EMBOSS`, `CONTOUR`
- Quantitative filter comparison: pixels changed, max increase/decrease, mean absolute change via NumPy + Pandas
- Direct pixel manipulation using NumPy arrays (e.g., zeroing out a corner region)
- Building synthetic images from scratch (landscape scene, checkerboard pattern)

---

### 2. `Pixel Art & Image Processing with PIL.ipynb` — Pixel Art & 3D Color Images
A creative, task-based notebook focused on direct pixel manipulation and building images from raw NumPy arrays.

**Tasks:**
1. **Pixel Value Manipulation** — Open an image, extract the top-left corner, overwrite a 50×50 region with black (`[0,0,0]`), and compare before/after arrays
2. **3D Color Image Construction** — Build RGB images from scratch using `np.zeros((h, w, 3))`, painting regions with specific RGB values

**Pixel Art Project — American Flag:**
- 13 alternating red/white stripes: Old Glory Red `[191, 10, 48]` and white `[255, 255, 255]`
- Blue canton in the top-left: navy `[60, 59, 110]`
- 50 stars in alternating rows (5 rows of 6 + 4 rows of 5) using computed offsets — no hardcoded positions
- Each star is a `2×2` white pixel block
- Helper functions: `show_image()` and `save_image()` for display and export

**Coordinate reference used:**
```
top-left     → [0, 0]
top-right    → [0, width]
bottom-left  → [height, 0]
bottom-right → [height, width]
center       → [height//2, width//2]
```

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `Pillow (PIL)` | Core image I/O and operations |
| `NumPy` | Pixel array manipulation and analysis |
| `Matplotlib` | Image visualization |
| `Pandas` | Filter comparison summary tables |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pillow numpy matplotlib pandas
```

### Run the notebooks
```bash
jupyter notebook
```

Open either `.ipynb` file and run cells top to bottom. A sample image (`redbull.jpg`) is expected in the same directory for `Image-Processing-v2.ipynb` and the pixel art notebook.

---

## 💡 Key Takeaways

- Cropping does **not** alter pixel values — it shifts the coordinate origin to the crop region's top-left
- `EMBOSS` and `CONTOUR` filters produce the most extreme pixel-level changes; `BLUR` and `SHARPEN` are subtle
- NumPy arrays with shape `(height, width, 3)` are the backbone of custom RGB image creation
- Pixel art (like a flag) can be generated entirely from math — no design tools needed

---

## 👩‍💻 Author

**Shikshya** · [GitHub: s3achan](https://github.com/s3achan)
