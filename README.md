# Fashion-MNIST UMAP Exploration

An interactive Jupyter notebook exploring dimensionality reduction on
[**Fashion-MNIST**](https://github.com/zalandoresearch/fashion-mnist) and the classic
**MNIST** handwriting dataset using UMAP, with comparisons against PCA and t-SNE.

## Overview

The notebook walks through a classic UMAP demonstration on image data:

1. **Load data** — Fetches MNIST and Fashion-MNIST from OpenML (`fetch_openml`) and
   subsamples 10,000 examples per dataset for speed.
2. **UMAP embedding of MNIST** — Visualizes the 2D projection of handwritten digits,
   colored by true label.
3. **Compare against PCA and t-SNE** — Side-by-side projections highlighting how each
   technique handles the data.
4. **Fashion-MNIST** — Same UMAP treatment applied to clothing images, showing how the
   visually similar categories (e.g. shirt vs. coat) are harder to separate.
5. **Effect of UMAP parameters** — How `min_dist` changes cluster tightness and separation.
6. **3D UMAP embedding** — An interactive Plotly 3D projection of Fashion-MNIST where each
   of the 10 clothing classes (T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt,
   Sneaker, Bag, Ankle boot) is labeled by name.

## Requirements

- Python 3.8+
- `numpy`
- `matplotlib`
- `scikit-learn`
- `umap-learn`
- `plotly`
- `pandas`
- `jupyter` / `notebook`

Install the dependencies with:

```bash
pip install numpy matplotlib scikit-learn umap-learn plotly pandas jupyter
```

## Usage

```bash
jupyter notebook Fashion_MNIST.ipynb
```

> **Note:** The notebook downloads data from OpenML the first time it runs, so it requires
> internet access. Run it locally or in Google Colab if your environment restricts outbound
> network access.

## Key Takeaways

- UMAP cleanly separates the 10 MNIST digits into well-isolated clusters.
- Fashion-MNIST is visibly harder: 2D pixel similarity is not enough to fully separate
  visually similar garments such as shirts from coats.
- UMAP typically runs faster than t-SNE on this scale and preserves more global structure.
- Embedding in 3D gives UMAP more room to separate classes that overlap in 2D.