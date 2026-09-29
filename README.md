# OHDSI 2026 Global Symposium Tutorial (Imaging WG)

### Bringing FAIR to Imaging Research with the Medical Imaging OMOP Extension

| | |
|---|---|
| **Date** | Monday, October 20, 2026 |
| **Time** | 08:00–12:00 |
| **Environment** | Google Colab (no local install) |
| **Agenda** | [tutorial-agenda.docx](https://docs.google.com/document/d/1DmHRaefxGvuvXr3d9bzi7w43XXjcn3uS/edit?usp=sharing&ouid=109112190111809847277&rtpof=true&sd=true) |
| **Slide plan** | [MI-CDM Tutorial OHDSI 2026 – Slide Plan](https://docs.google.com/document/d/145PchSsbl7MAWGUyZgR49wpqxBbOhTHOkF0G5J87kgg/edit?usp=sharing) |


## Repository structure

```
OHDSI2026-Tutorial/
├── README.md
└── notebooks/
    ├── 01_DICOM_to_MI-CDM_ETL.ipynb      # Hands-on I
    └── 02_Image_Derived_Features.ipynb   # Hands-on II
```

## Notebooks

Each section of the notebooks is labelled with the ImageWG wiki flow-chart step it implements [1].

| Notebook | Wiki steps | What you build | Runtime | Open |
|---|---|---|---|---|
| **01. From DICOM archive to MI-CDM** | 1–6 | Index 100 RSNA CR files, extract and characterize DICOM headers, load the DICOM vocabulary, and ETL into `PERSON`, `PROCEDURE_OCCURRENCE`, `IMAGE_OCCURRENCE`, `MEASUREMENT` and `IMAGE_FEATURE`; data-quality checks and an imaging search query | CPU is fine (~5 min incl. download) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dr-you-group/OHDSI2026-Tutorial/blob/main/notebooks/01_DICOM_to_MI-CDM_ETL.ipynb) |
| **02. Image-derived features with provenance** | 7–11 | Run TorchXRayVision classification and segmentation, store findings in `IMAGE_FEATURE` with values in `OBSERVATION`, keep provenance (`alg_system`, `alg_datetime`), run data-quality checks, and download the complete SQLite database | T4 GPU recommended | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dr-you-group/OHDSI2026-Tutorial/blob/main/notebooks/02_Image_Derived_Features.ipynb) |

## Running in Google Colab

1. **Open a notebook** — any of these works:
   - Click an **Open in Colab** badge above.
   - In Colab: **File → Open notebook → GitHub**, enter `dr-you-group/OHDSI2026-Tutorial`, and pick the notebook.
   - Download the `.ipynb` and use **File → Upload notebook**.
2. **Sign in** with a Google account and choose **File → Save a copy in Drive** to keep your changes.
3. **Choose a runtime** — for notebook 02: **Runtime → Change runtime type → T4 GPU**.
4. **Run all** — **Runtime → Run all**. Notebook 01 downloads the data and the vocabulary itself.
5. **Starting notebook 02 in a new runtime?** The catch-up cell in section 0 rebuilds the notebook 01 database automatically, so you can start there if you fell behind.
6. **Take the database home** — the last cell of notebook 02 downloads `omop_micdm.db` (notebooks 01 + 02 in one SQLite file).

## Resources

| | |
|---|---|
| **Format** | Follow the ImageWG wiki ETL flow chart step by step [1] |
| **Data** | RSNA Pneumonia Detection Challenge 2018 — a 100-file CR subset fetched in Colab [2] |
| **Model** | TorchXRayVision [3]: DenseNet-121 (classification), PSPNet (chest segmentation) |

## References

1. Medical Imaging Extension Conventions. (n.d.). GitHub. Retrieved September 29, 2026, from https://github.com/OHDSI/ImageWG/wiki/Medical-Imaging-Extension-Conventions
2. Anouk Stein, MD, Carol Wu, Chris Carr, George Shih, Jamie Dulkowski, kalpathy, Leon Chen, Luciano Prevedello, Marc Kohli, MD, Mark McDonald, Peter, Phil Culliton, Safwan Halabi MD, and Tian Xia. RSNA Pneumonia Detection Challenge. https://www.kaggle.com/competitions/rsna-pneumonia-detection-challenge, 2018. Kaggle.
3. Cohen, J. P., Viviano, J. D., Bertin, P., Morrison, P., Torabian, P., Guarrera, M., Lungren, M. P., Chaudhari, A., Brooks, R., Hashir, M., & Bertrand, H. (2021). TorchXRayVision: A library of chest X-ray datasets and models (arXiv:2111.00595). arXiv. https://doi.org/10.48550/arXiv.2111.00595
