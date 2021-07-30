## This is the repo for the Datathon hosted by Galvanize. The objective is to use data fron NY Independing System Operator (ISO), which operates in the energy market, and extract insights and patterns.

The [dataset](https://www.nyiso.com/energy-market-operational-data) used for this project are the real-time Price and Load data provided by NYISO. Sever jupyter notebooks are created with prefix which corresponds to the work flow/steps.
- 1a_load_data_processing.ipynb and 1b_price_data_processing.ipynb are the data processing notebooks.
- 2_time_series_analysis analyzed the Price data using the opens source Libray Kats. (Note: this was ran on COLAB because the PaperSpace instance couldn't support the installation for `Kats`)
- 3_data_viz is the Dash plot that puts everything together for some high level data visualization.

The Dash app does take some time to load and udpate. It has one drop down tab where the user can select the zone/region and the plots will update accordingly. The Stability plot is based on the time series feature (TSFeature) extraction from `Kats` (click [here](https://github.com/facebookresearch/Kats) for more details), and is a measure of how stabile (aka, predictable) the price time series are. A screen snapshot of the dashboard is shown below.

<img width="912" alt="NYISO dash_board" src="https://user-images.githubusercontent.com/7095892/127601325-2d09d58a-0b2d-4d9e-a2f6-6349cae9dd31.png">
