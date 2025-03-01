---
title: "Exercise: Changepoint Detection in Tumor Data"
author: "Arnaud Liehrmann & Guillem Rigaill"
output: html_document
---

## Exercise: Changepoint Detection in Tumor Data

In this exercise, you will analyze tumor patient data, including **normalized copy number profiles** and **changepoint annotations of subregions**. Each subregion is labeled as either:

-   **"normal"**: No changepoint detected.
-   **"breakpoint"**: At least one changepoint detected.

The dataset can be downloaded here: <https://filesender.renater.fr/?s=download&token=aa63a130-8cbf-409d-bec8-578404a45a0e>.

A more detailed description of the columns can be found in the following reference: [CRAN neuroblastoma package documentation](https://cran.r-project.org/web/packages/neuroblastoma/neuroblastoma.pdf).

------------------------------------------------------------------------

## I) Local Analysis (Within Annotated Regions)

1.  **Run and evaluate** the performance of the **CUSUM algorithm** on the annotated regions, after estimating the variance within these same regions.

2.  **Further investigations:**

    -   **(2.A)** Re-evaluate the performance of the algorithm by **introducing a minimum segment length constraint**.
    -   **(2.B)** Use a subset of the **"normal"** regions to **calibrate the penalty**, then re-evaluate performance on the remaining regions.
    -   **(2.C) BONUS**: Implement the **likelihood ratio test** for the **i.i.d. Gaussian model with unknown variance**, then evaluate its performance on the annotated regions. You may also introduce a **minimum segment length constraint**.

------------------------------------------------------------------------

## II) Global Analysis (Across Complete Profiles)

1.  **Run and evaluate** the **OP (Optimal Partitioning) algorithm** using the **SIC penalty** $2\sigma^2 \log(n)$ on the full profiles, after estimating the variance of these profiles. Compare the results with those from the Local Analysis.

2.  **Further investigations:**

    -   **(A)** Re-evaluate the performance of the algorithm by **introducing a minimum segment length constraint**.
    -   **(B)** Exploit the **"elbow" phenomenon** to adaptively calibrate the penalty using the method described in *Lavielle (2005)* ([Link to paper](https://inria.hal.science/inria-00070662/document)). Compare the performance of this adaptive procedure with the **SIC penalty**.

## Contact Information

-   **Guillem Rigaill**: [guillem.rigaill\@inrae.fr](mailto:guillem.rigaill@inrae.fr)
-   **Arnaud Liehrmann**: [arnaud.liehrmann\@sorbonne-universite.fr](mailto:arnaud.liehrmann@sorbonne-universite.fr)
