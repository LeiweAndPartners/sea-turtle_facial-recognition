# Sea Turtle Facial Recognition with LightGlue

Demonstration notebooks for identifying individual sea turtles from facial imagery using **SIFT keypoints + LightGlue matching**.

[![Open Notebook 2 in Colab](https://img.shields.io/badge/Open%20Notebook%202-Colab-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/2_turtle_identification.ipynb)
[![Open Notebook 1 in Colab](https://img.shields.io/badge/Open%20Notebook%201-Colab-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/1_build_reference_library.ipynb)
[![Presented At AI Tinkerers](https://img.shields.io/badge/Presented%20At-AI%20Tinkerers-7B61FF)](https://hong-kong.aitinkerers.org/talks/rsvp_CKcqvusIVsI)
[![Featured In Community Spotlight #16](https://img.shields.io/badge/Featured%20In-Community%20Spotlight%20%2316-0EA5E9)](https://post-training.aitinkerers.org/p/community-spotlights-issue-16)

[Open Notebook 2 in Colab](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/2_turtle_identification.ipynb) • [Open Notebook 1 in Colab](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/1_build_reference_library.ipynb) • [Presented At](https://hong-kong.aitinkerers.org/talks/rsvp_CKcqvusIVsI) • [Featured In (AI Tinkerers Spotlight #16)](https://post-training.aitinkerers.org/p/community-spotlights-issue-16)

---

## 📖 Context

This repository accompanies Marcus Leiwe’s AI Tinkerers Hong Kong talk:
**“LightGlue: High-Performance Feature Matching.”**

The project shows a practical end-to-end identity-matching workflow:
- local feature extraction with SIFT,
- neural sparse matching with LightGlue,
- notebook-first experimentation in Google Colab.

---

## 🚀 What This Demo Covers

- Building a reusable reference library from known turtles
- Matching new turtle images against the reference set
- Ranking candidates with confidence-distribution scoring (AUC-based in notebook)
- Producing interpretable notebook outputs for workshop/demo settings

---

## 🧭 Repository Structure

```text
.
├── 1_build_reference_library.ipynb
├── 2_turtle_identification.ipynb
├── pyproject.toml
└── data/
	 ├── initial_database/
	 └── new_samples/
```

---

## 🛠️ Quick Start (Google Colab)

### Recommended flow (focus on Notebook 2)

1. Run Notebook 1 once to create `reference_library.pkl`  
	[Open Notebook 1](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/1_build_reference_library.ipynb)

2. Open Notebook 2 (main demo notebook)  
	[Open Notebook 2](https://colab.research.google.com/github/LeiweAndPartners/sea-turtle_facial-recognition/blob/main/2_turtle_identification.ipynb)

3. In Colab, enable GPU:  
	**Runtime → Change runtime type → Hardware accelerator → GPU**

4. Ensure these assets exist before running full Notebook 2:
	- `reference_library.pkl` in repo root
	- query images in `data/new_samples/` (`.jpg` or `.JPG`)

5. Run Notebook 2 top-to-bottom.

### Talk Colab Link

From the AI Tinkerers event page:  
[Interactive Colab demo](https://colab.research.google.com/drive/1DOa6nbE_a72vGrxin5pnfOGpvPNsvdj-)

---

## 🎯 Notebook Responsibilities

### 1) Build Reference Library
Notebook: `1_build_reference_library.ipynb`

- Loads known turtle images from `data/initial_database/`
- Extracts SIFT features via LightGlue’s SIFT module
- Saves serialized features as `reference_library.pkl`

### 2) Run Identification (Primary)
Notebook: `2_turtle_identification.ipynb`

- Loads `reference_library.pkl`
- Loads query images from `data/new_samples/`
- Matches each query against each reference image using LightGlue
- Produces ranked matches and summary outputs

---

## ⚠️ Common Colab Issues

1. **Missing `reference_library.pkl`**  
	Run Notebook 1 first (or upload the file manually).

2. **No query images found**  
	Confirm images are inside `data/new_samples/` with `.jpg`/`.JPG` extensions.

3. **Slow runtime**  
	Confirm GPU is enabled.

4. **State reset**  
	Colab storage is ephemeral; rerun setup and re-upload files if needed.

---

## 💻 Local Setup (Poetry)

If you prefer local notebooks:

1. Install dependencies: `poetry install`
2. Launch Jupyter: `poetry run jupyter notebook`
3. Run notebooks in this order:
	- `1_build_reference_library.ipynb`
	- `2_turtle_identification.ipynb`

---

## 🔗 Links

- Repository: https://github.com/LeiweAndPartners/sea-turtle_facial-recognition
- Talk page: https://hong-kong.aitinkerers.org/talks/rsvp_CKcqvusIVsI
- AI Tinkerers Community Spotlight #16: https://post-training.aitinkerers.org/p/community-spotlights-issue-16
- LightGlue: https://github.com/cvg/LightGlue
