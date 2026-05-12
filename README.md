# FOCI Dataset – Object Counting

The **[foci_counting_example.ipynb](https://github.com/imke-kilab/foci-counting/blob/main/foci_counting_example.ipynb)** notebook demonstrates two approaches for counting radiation-induced DNA damage foci in fluorescence microscopy images using the [FOCI dataset](https://zenodo.org/records/19222986) (446 images, pre-cropped and split into train/val/test).

| # | Approach | Idea |
|---|----------|------|
| 1 | **YOLO** (YOLOv8n) | Detect individual foci with bounding boxes, count detections |
| 2 | **U-Net Density Map** | Regress a density map via a U-Net and integrate to obtain the count |

## Run the notebook

Run the demo notebook in google Colab (no setup required):

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/imke-kilab/foci-counting/blob/main/foci_counting_example.ipynb
)

The notebook installs all dependencies automatically. Key packages: `ultralytics`, `torch`, `lightning`, [`density_maps`](https://pypi.org/project/density-maps/), `albumentations`.

> ⚠️ **GPU recommended.** Both training steps benefit from GPU acceleration.
> The density-map regression (Approach 2) takes **over 2 hours on CPU** but only a few minutes on GPU.

## Dataset

The dataset is hosted on [Hugging Face](https://huggingface.co/datasets/Im-KI/cell-foci) and cloned automatically when running the notebook. More details and the full dataset description can be found on [Zenodo](https://zenodo.org/records/19222986).

## Authors

See the [dataset page on Zenodo](https://zenodo.org/records/19222986) for authors and citation information.

## License

This project is licensed under the GNU Affero General Public License v3.0 (AGPL-3.0).

It uses Ultralytics (AGPL-3.0). Any use of this notebook and its components must comply with the terms of that license.
