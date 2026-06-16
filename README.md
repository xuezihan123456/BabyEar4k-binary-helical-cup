# BabyEar4k 二分类子集：耳轮型 vs 杯状耳

# BabyEar4k Binary Subset: Helical-Type Ear vs Cup Ear

## 中文说明

### 数据来源

本仓库整理自 BabyEar4k 公开数据集，用于耳轮型与杯状耳二分类研究。BabyEar4k 的原始诊断/类别标注由专业医生完成；本子集在公开数据和既有标注基础上进行清理筛选，仅保留耳轮型和杯状耳两类图像。

耳轮型和杯状耳均属于耳廓畸形类别。本数据集不包含“正常耳/健康耳”类别。

### 数据文件

为提高 GitHub 上传稳定性，图像按类别拆成多个小压缩包，mask 按类别打包：

- `data/images_cup_ear_part1.zip`
- `data/images_cup_ear_part2.zip`
- `data/images_cup_ear_part3.zip`
- `data/images_cup_ear_part4.zip`
- `data/images_helical_type_part1.zip`
- `data/images_helical_type_part2.zip`
- `data/images_helical_type_part3.zip`
- `data/images_helical_type_part4.zip`
- `data/masks_cup_ear.zip`
- `data/masks_helical_type.zip`

每个 zip 解压后都包含相对路径。把所有压缩包解压到同一个目录后，应得到：

```text
images/
  cup_ear/
  helical_type/
masks/
  cup_ear/
  helical_type/
```

`metadata/manifest.csv` 中的 `image_path` 和 `mask_path` 是相对解压后根目录的路径。

### 数据规模

| 项目 | 数量 |
| --- | ---: |
| 总样本数 | 2493 |
| 耳轮型 | 1186 |
| 杯状耳 | 1307 |
| dev 样本 | 2003 |
| locked test 样本 | 490 |
| 排除歧义样本 | 8 |

### 目录结构

```text
.
+-- README.md
+-- data/
|   +-- images_cup_ear_part1.zip
|   +-- images_cup_ear_part2.zip
|   +-- images_cup_ear_part3.zip
|   +-- images_cup_ear_part4.zip
|   +-- images_helical_type_part1.zip
|   +-- images_helical_type_part2.zip
|   +-- images_helical_type_part3.zip
|   +-- images_helical_type_part4.zip
|   +-- masks_cup_ear.zip
|   +-- masks_helical_type.zip
+-- metadata/
    +-- excluded_ambiguous.csv
    +-- fixed_test_current_490.csv
    +-- manifest.csv
```

### 标签定义

| label | class_dir | 中文类别 | 英文说明 |
| ---: | --- | --- | --- |
| 0 | `helical_type` | 耳轮型 | helical-type ear deformity |
| 1 | `cup_ear` | 杯状耳 | cup ear deformity |

### 子集构建说明

- 原始来源：BabyEar4k 公开数据集。
- 标注依据：公开数据集中的专业医生诊断标注。
- 清理规则：保留文件名/标注中明确属于“耳轮型”或“杯状耳”的样本；排除同时包含两类关键词的歧义样本。
- 图像处理：使用本项目二分类实验中的预处理耳图和对应二值 mask。
- 固定测试集：`metadata/manifest.csv` 中 `split=test_locked` 的样本来自 `metadata/fixed_test_current_490.csv`。

### 引用

建议引用原始数据集论文：

- Ren L.-J. et al., *A publicly available newborn ear shape dataset for medical diagnosis of auricular deformities*, Scientific Data. DOI: https://doi.org/10.1038/s41597-023-02834-4

使用或再分发图像时，请同时遵守 BabyEar4k 原始数据集及论文页面的许可和引用要求。

## English Description

### Data Source

This repository contains a curated binary-classification subset derived from the publicly available BabyEar4k dataset. It is intended for classifying helical-type ear deformity and cup ear deformity. The original diagnosis/category annotations in BabyEar4k were provided by professional physicians. For this subset, the public data and existing annotations were cleaned and filtered to retain only helical-type ear and cup ear images.

Both helical-type ear and cup ear are auricular deformity categories. This dataset does not include a normal-ear or healthy-ear class.

### Data Files

For more stable GitHub upload, the image files are split into several small archives by class, and the masks are packaged by class:

- `data/images_cup_ear_part1.zip`
- `data/images_cup_ear_part2.zip`
- `data/images_cup_ear_part3.zip`
- `data/images_cup_ear_part4.zip`
- `data/images_helical_type_part1.zip`
- `data/images_helical_type_part2.zip`
- `data/images_helical_type_part3.zip`
- `data/images_helical_type_part4.zip`
- `data/masks_cup_ear.zip`
- `data/masks_helical_type.zip`

Each zip archive stores relative paths. After extracting all archives into the same directory, the expected structure is:

```text
images/
  cup_ear/
  helical_type/
masks/
  cup_ear/
  helical_type/
```

The `image_path` and `mask_path` fields in `metadata/manifest.csv` are relative to the extracted dataset root.

### Dataset Size

| Item | Count |
| --- | ---: |
| Total samples | 2493 |
| Helical-type ear | 1186 |
| Cup ear | 1307 |
| Dev samples | 2003 |
| Locked test samples | 490 |
| Excluded ambiguous samples | 8 |

### Repository Structure

```text
.
+-- README.md
+-- data/
|   +-- images_cup_ear_part1.zip
|   +-- images_cup_ear_part2.zip
|   +-- images_cup_ear_part3.zip
|   +-- images_cup_ear_part4.zip
|   +-- images_helical_type_part1.zip
|   +-- images_helical_type_part2.zip
|   +-- images_helical_type_part3.zip
|   +-- images_helical_type_part4.zip
|   +-- masks_cup_ear.zip
|   +-- masks_helical_type.zip
+-- metadata/
    +-- excluded_ambiguous.csv
    +-- fixed_test_current_490.csv
    +-- manifest.csv
```

### Label Definition

| label | class_dir | Chinese label | English description |
| ---: | --- | --- | --- |
| 0 | `helical_type` | 耳轮型 | helical-type ear deformity |
| 1 | `cup_ear` | 杯状耳 | cup ear deformity |

### Subset Construction

- Original source: the publicly available BabyEar4k dataset.
- Annotation basis: physician-provided diagnosis annotations in the public dataset.
- Cleaning rule: samples explicitly labeled as helical-type ear or cup ear were retained; samples whose filenames contained both category keywords were excluded as ambiguous.
- Image processing: this subset uses the preprocessed ear images and corresponding binary masks used in the binary-classification experiments.
- Fixed test set: samples with `split=test_locked` in `metadata/manifest.csv` come from `metadata/fixed_test_current_490.csv`.

### Citation

Please cite the original dataset paper:

- Ren L.-J. et al., *A publicly available newborn ear shape dataset for medical diagnosis of auricular deformities*, Scientific Data. DOI: https://doi.org/10.1038/s41597-023-02834-4

When using or redistributing the images, please also follow the license and citation requirements of the original BabyEar4k dataset and paper page.
