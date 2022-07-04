## Repo for the Datathon hosted by Galvanize. 

### Objective
The objective is to leverage the data from NY Independent System Operator (ISO), which operates in the energy market, and extract insights and patterns.

### Technologies
The project was developed using Paperspace Gradient notebook (courtesy of Galvanize), RapidsAI, Dash, Plotly, and Kats.

### Description
The [dataset](https://www.nyiso.com/energy-market-operational-data) used for this project are the real-time Price and Load data provided by NYISO. The raw data are not part of this repo(due to size constraint), but there is a file at `processed_data/price_volatility_jan_july.csv` that is the output from the time series modeling. 

Several jupyter notebooks are created with prefix that corresponds to the work flow/steps.

- `1a_load_data_processing.ipynb` and `1b_price_data_processing.ipynb` are the data processing notebooks.
- `2_time_series_analysis.ipynb` analyzed the Price data using the opens source Libray Kats (Note: this was ran on COLAB because Paperspace instance couldn't support the installation for `Kats`).
- `3_data_viz.ipynb` is the Dash plot that bundles everything together for some high level data visualization.

The Dash app does take some time to load and udpate. It has one drop down tab where the user can select the zone/region and the plots will update accordingly. The Entropy metric is based on the time series feature (TSFeature) extraction from `Kats` (click [here](https://github.com/facebookresearch/Kats) for more details), and is calculated as Shannon entropy as it captures the uncertainty in a distribution. The higher the entropy the more unpredictable the price time series become. A heatmap is provided to illustrate the daily consumption of load for each zone to help identify hot spots. The screen snapshot of the dashboard is shown below.

<img width="1231" alt="Screen Shot 2021-08-05 at 11 37 21 PM" src="https://user-images.githubusercontent.com/7095892/128461742-11c0caa2-7694-4666-bced-3807da152377.png">

#### REFERENCES
1. Kats documentation, https://facebookresearch.github.io/Kats/api/kats.tsfeatures.tsfeatures.html
2. Plotly home page, https://plotly.com/graphing-libraries/
