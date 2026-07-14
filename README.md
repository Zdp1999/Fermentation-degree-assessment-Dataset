# Congou Black Tea Fermentation Degree Dataset

## Overview

This repository contains a curated public subset of an RGB image dataset for the non-destructive assessment of Congou black tea fermentation degree. The images represent five controlled fermentation reference times from 0 to 4 h and are organized as a balanced five-class image-classification dataset.

The dataset is associated with the manuscript *A lightweight spatial-frequency dual-domain collaborative network for non-destructive assessment of Congou black tea fermentation degree*.

## Dataset summary

- Total images: **3,600**
- Number of classes: **5**
- Images per class: **720**
- Image format: **JPG**
- Image size: **408 x 408 pixels**
- Color mode: **RGB**

| Folder | Fermentation reference time | Number of images |
| --- | ---: | ---: |
| [`00/`](./00/) | 0 h | 720 |
| [`10/`](./10/) | 1 h | 720 |
| [`20/`](./20/) | 2 h | 720 |
| [`30/`](./30/) | 3 h | 720 |
| [`40/`](./40/) | 4 h | 720 |

These time points are controlled processing references used as class labels; they should not be interpreted as universal fermentation-quality grades for all tea cultivars or processing conditions.

## Directory structure

```text
.
|-- 00/
|-- 10/
|-- 20/
|-- 30/
|-- 40/
`-- README.md
```

## File naming

Most images follow this naming convention:

```text
<class>-<source_id>_tile_<row>_<column>.jpg
```

For example, `20-10_tile_2_3.jpg` is a tile from source image group 10 in the 2 h fermentation class. Each source image group contains a `5 x 6` grid of 30 tiles, with row indices from 0 to 4 and column indices from 0 to 5.

Known filename note: the 30 files belonging to source group 13 in the `00` class contain an extra space before `_tile`, for example `00-13 _tile_0_0.jpg`. Data-loading code should account for this filename variation.

## Recommended dataset splitting

Tiles originating from the same source image are visually related. To prevent data leakage, create training, validation and test partitions at the **source-image-group level**, using the class and `source_id` encoded in each filename. Do not randomly place tiles from the same source group into different partitions.

This repository does not define an official training, validation or test split.

## Relationship to the manuscript dataset

This GitHub release contains **3,600 images** and is a curated public subset of the **6,480-image processed dataset** described in the associated manuscript. Results should report clearly whether they use this public subset or the complete manuscript dataset.

## Associated manuscript

**Title:** A lightweight spatial-frequency dual-domain collaborative network for non-destructive assessment of Congou black tea fermentation degree

**Authors:** Dengpeng Zou, Fang Qi, Jingru Qin, Yisen Kang and Zhe Tang

No DOI or final publication details are currently specified in this repository. If you use this dataset, please cite the associated article once its bibliographic information becomes available and cite this dataset repository with the version or commit used in your work.

## License

This dataset is licensed under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You may share and adapt the dataset for any purpose, provided that appropriate credit is given, a link to the license is included and any changes are indicated.
