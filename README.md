# OHDSI 2026 Global Symposium Tutorial (Image WG)

- Title: Bringing FAIR to Imaging Research with the Medical Imaging OMOP Extension
- Date: Monday, October 20, 2026
- Time: 08:00–12:00

## Agenda

- **Tutorial agenda:** [tutorial-agenda.docx](https://docs.google.com/document/d/1DmHRaefxGvuvXr3d9bzi7w43XXjcn3uS/edit?usp=sharing&ouid=109112190111809847277&rtpof=true&sd=true)
- **Tutorial slide plan:** [MI-CDM Tutorial OHDSI 2026 – Slide Plan.docx](https://docs.google.com/document/d/145PchSsbl7MAWGUyZgR49wpqxBbOhTHOkF0G5J87kgg/edit?usp=sharing)

## Resources

**Environment:** Google Colab

**Format:** Follow the ImageWG wiki ETL flow chart step by step [1]

**Data:** RSNA Pneumonia Detection Challenge 2018, a 100-file CR subset fetched in Colab. [2]

**Model:** TorchXRayVision [3]

- DenseNet-121 (classification)
- PSPNet (chest segmentation)



## References
1. Medical Imaging Extension Conventions. (n.d.). GitHub. Retrieved September 29, 2026, from https://github.com/OHDSI/ImageWG/wiki/Medical-Imaging-Extension-Conventions
2. Anouk Stein, MD, Carol Wu, Chris Carr, George Shih, Jamie Dulkowski, kalpathy, Leon Chen, Luciano Prevedello, Marc Kohli, MD, Mark McDonald, Peter, Phil Culliton, Safwan Halabi MD, and Tian Xia. RSNA Pneumonia Detection Challenge. https://www.kaggle.com/competitions/rsna-pneumonia-detection-challenge, 2018. Kaggle.
3. Cohen, J. P., Viviano, J. D., Bertin, P., Morrison, P., Torabian, P., Guarrera, M., Lungren, M. P., Chaudhari, A., Brooks, R., Hashir, M., & Bertrand, H. (2021). TorchXRayVision: A library of chest X-ray datasets and models (arXiv:2111.00595). arXiv. https://doi.org/10.48550/arXiv.2111.00595