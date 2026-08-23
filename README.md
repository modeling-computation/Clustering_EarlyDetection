# Statistical Framework for Early Warning Detection of Multiple Infectious Diseases

## Abstract

 Early detection of infectious disease outbreaks is essential for effective public health response, yet many diseases lack clear criteria for defining outbreak onset.
 This study proposes a statistical framework for early outbreak detection utilizing only reported case data, allowing application across diseases with different seasonal patterns. The framework comprises three stages.
 Initially, since outbreak patterns vary across diseases, outbreak periods are identified from historical disease patterns rather than fixed thresholds.
 Subsequently, K-means clustering is applied to time-series data to detect high-risk periods, with the third consecutive week defined as the early detection point.
 Finally, bootstrap resampling estimates the probability of an emerging outbreak, which is categorized into three warning levels, Caution (<5%), Alert (5%–10%), and Severe (>10%).
 This approach was evaluated utilizing surveillance data for Influenza, respiratory syncytial virus (RSV), hand, foot, and mouth disease (HFMD), and Norovirus infection (Norovirus) in the Republic of Korea.
 Estimated Influenza detection timings were compared with alerts issued by the Korea Disease Control and Prevention Agency (KDCA), while for RSV, HFMD, and Norovirus were compared with Hockey-stick regression breakpoints representing rapid increases in reported cases.
 For Influenza, estimated detection points closely matched KDCA alerts and occurred 2–3 weeks earlier in the 2017–2019 seasons. For RSV, HFMD, and Norovirus, estimated detections were broadly consistent with breakpoints.
 The probabilistic warning levels further captured elevated outbreak risk before comparison points and reflected seasonal uncertainty.
 Overall, the proposed framework enables outbreak monitoring across different diseases without predefined criteria and provides timely warning signals to support public health decision-making.

---

## Repository Structure

```text
Clustering_EarlyDetection/
├── app.py
├── config.py
├── requirements.txt
│
├── data/
│   ├── ILI_260126.xlsx
│   ├── ILI_TD_results.xlsx
│   ├── ILI_cusum_260126.xlsx
│   ├── ILI_short_history_under3y.xlsx
│   └── ILI_week_2015_2025.xlsx
│
├── src/
│   ├── __init__.py
│   ├── preprocessing.py
│   ├── clustering.py
│   ├── season_setting.py
│   └── visualization.py
│
└── images/
```

### File Description

- **`app.py`**  
  Main Streamlit application for running the early-warning analysis and visualizing the results.

- **`config.py`**  
  Configuration settings used by the application.

- **`data/`**  
  Contains epidemiological surveillance data and intermediate/result files used in the analysis.

- **`src/preprocessing.py`**  
  Data preprocessing and feature extraction, including cumulative-sum-based features and sliding-window feature construction.

- **`src/clustering.py`**  
  Clustering and early-warning detection procedures, including K-means clustering and bootstrap-based analyses.

- **`src/season_setting.py`**  
  Functions for defining epidemiological seasons and estimating season-specific temporal characteristics.

- **`src/visualization.py`**  
  Visualization functions for seasonal patterns and early-warning detection results.

- **`images/`**  
  Images and figures used in the repository or documentation.

- **`requirements.txt`**  
  Python package dependencies required to run the project.

---

## Data Description and Sources

This study uses infectious-disease surveillance data provided by the **Korea Disease Control and Prevention Agency (KDCA)**. The datasets include influenza-like illness (ILI), hand, foot, and mouth disease (HFMD), respiratory syncytial virus (RSV), and norovirus surveillance data.

### Data Sources

#### Influenza

**[KDCA] Korea Disease Control and Prevention Agency (KDCA). Influenza.**

https://www.kdca.go.kr/kdca/3495/subview.do

#### Influenza-like Illness (ILI)

**[ILI] Korea Disease Control and Prevention Agency (KDCA). Influenza-like illness (ILI) surveillance data.**

https://dportal.kdca.go.kr/pot/is/st/influ.do

#### Hand, Foot, and Mouth Disease (HFMD)

**[HFMD] Korea Disease Control and Prevention Agency (KDCA). Hand, foot, and mouth disease (HFMD) surveillance data.**

https://dportal.kdca.go.kr/pot/is/st/hfmd.do

#### Respiratory Syncytial Virus (RSV)

**[RSV] Korea Disease Control and Prevention Agency (KDCA). Respiratory syncytial virus (RSV) surveillance data.**

https://dportal.kdca.go.kr/pot/is/st/ari.do

#### Norovirus

**[Noro] Korea Disease Control and Prevention Agency (KDCA). Norovirus surveillance data.**

https://dportal.kdca.go.kr/pot/is/st/gstrnftn.do
