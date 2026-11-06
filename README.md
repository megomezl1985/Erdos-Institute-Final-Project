# Estimating Implied Volatilities via Kernel Smoothing

### Mauricio Gómez López

**Erdös Institute — Quantitative Finance, Fall 2026**

---

The goal of this project is to perform a systematic comparison between two methods for estimating implied volatilities and constructing models of volatility curves:

*   The S-1D kernel smoothing method.
*   The Heston model.

The *S-1D kernel smoothing method* is a simplified version of the kernel smoothing method introduced in the following paper, which we also included in this repository:

> M. Ulrich, S. Walther, *Option-implied information: What's the vol surface got to do with it?*, Review of Derivatives Research (2020) 23:323–355.

The code in this project's Jupyter notebook can be used to compare the accuracy of the 1-SD kernel smoothing method and the Heston model for estimating implied volatilities on any quote date in our dataset.

Below, we provide an overview of this project and guidelines for running the analysis.

## 1. Data

In this project, we use end-of-day Tesla stock option data from the years 2019 and 2022. This dataset is available at the following link:

https://www.kaggle.com/datasets/kylegraupe/tsla-daily-eod-options-quotes-2019-2022

The dataset can also be downloaded from the following Google Drive folder:

https://drive.google.com/drive/folders/1NAmuCUru2C9XKaKmHgzfES-PoFzS-iaF?usp=sharing

## 2. Project Overview

In the list below, we briefly describe the contents of each section of this project's Jupyter notebook.

*   In Section 1, we provide an overview of kernel smoothing and introduce the S-1D kernel smoothing method.
*   In Section 2, we explain how to determine the optimal bandwidth parameter for the S-1D kernel smoothing method.
*  In Section 3, we compare the Heston model with the S-1D kernel smoothing method. We can perform this comparison for any quote date available in this project's dataset.
* Finally, in Section 4, we provide some conclusions from our analysis.

## 3. How to run the analysis

The user can reproduce this project's analysis by going through the following steps:

1.   Run Code Cells 0 and 1. Code Cell 1 contains all the Black-Scholes functions we use in this project.  
2.   Upload the Tesla stock option dataset to the Jupyter notebook.
3.  Run Code Cells 5 and 6. These code cells will download and clean up the dataset.
4. Code Cell 7 displays the list of all possible quote dates in our dataset. Additionally, the user can find the index for a specific quote date using the first line of code in this cell.
5. Run Code Cell 9. This cell contains the function produced by the S-1D kernel smoothing method for computing estimates of implied volatilities.
6. In Code Cell 10, the user can adjust the quote date (qd) in the first line of code. This date will serve as the reference date for comparing the Heston model with the S-1D kernel smoothing method.
7. Find the optimal bandwidth parameter for the S-1D kernel smoothing method for the quote date fixed in the previous step (Code Cells 11 and 12).
8. Run the Heston pricing function (Code Cell 13).
9. Calibrate the Heston model using the data from the quote date we fixed (Code Cell 15).
10. Finally, we compare the performance of the Heston model and the S-1D kernel smoothing method on the chosen quote date:

*   *Graphical comparison:* Code Cell 16 displays side-by-side the volatility curve models produced by the Heston model and the S-1D kernel smoothing method for each time to expiration available on our chosen quote date.
*   *Error comparison:* Code Cell 17 computes the root mean squared errors (RMSE) for the volatility curve models produced by the Heston model and the S-1D kernel smoothing method on our chosen quote date.

The project's executive summary includes a table listing the RMSEs for the Heston model and the S-1D kernel smoothing method for ten different quote dates. For each date in this table, the S-1D kernel smoothing method produced a lower RMSE than the Heston model. The outcome seems to be the same for any other quote date not listed in this table, which the user can verify by running the above analysis for any quote date fixed in Step 6.





