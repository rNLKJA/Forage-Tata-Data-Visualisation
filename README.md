# Forage · Tata Data Visualisation

My work from the [Tata Data Visualisation: Empowering Business with Effective Insights job simulation](https://www.theforage.com/simulations/tata/data-visualisation-p5xo) on Forage, completed in October 2022.

The simulation casts you as a consultant to an online retailer whose CEO and CMO want to know what drives revenue and where to expand. Its four modules ask you to anticipate the leaders' questions, choose the right chart for each request, build the visuals in Tableau or Power BI, and present the findings.

## What is in this repo

| Path | What it is |
| --- | --- |
| `1-framing/framing-the-business-scenario.ipynb` | My first look at the UCI Online Retail data, ending with the questions I drafted for the CEO and CMO. |
| `2-choosing-visuals/chart-choices.md` | The chart I chose for each of five requests, and why. |
| `3-creating-visuals/data-cleanup.ipynb` | Removes returns and invalid prices before any analysis and exports a clean CSV. |
| `3-creating-visuals/tata-data-viz.twb` | My Tableau workbook, with the four requested views and a dashboard. The data is not packaged with it. |
| `requirements.txt` | The Python packages the notebooks import. |
| `data/README.md` | Which files go in `data/` and where they come from. |

## The questions I drafted

Before drawing any charts I wrote down the questions I expected the two leaders to ask.

Quantitative questions:

- Which country has the highest ROI?
- What are the top 10 stocks, and how profitable are they?
- Who are our largest potential partners in future?
- What are the top-selling products?

Qualitative questions:

- Do buyers in a particular country prefer particular products? For example, are most of our French buyers looking at children's products?
- Why do we have so many orders from the United Kingdom?
- Why did we have fewer sales in December 2011 than in December 2010?
- Why did sales peak in November 2011?

## What I found

Removing returns (a quantity below 1) and invalid prices (a unit price of 0 or less) took the data from 541,909 rows to 530,104. The workbook has one view for each of the four requests, which cover 2011 revenue by month, the top 10 countries by revenue, the top 10 customers by revenue and demand by country on a map. A dashboard brings the four views together. In the monthly view, revenue rises from September and peaks in November 2011.

## Running it

1. Install the packages with `pip install -r requirements.txt`.
2. Download the [Online Retail data set](https://archive.ics.uci.edu/dataset/352/online+retail) from the UCI Machine Learning Repository and save `Online Retail.xlsx` in `data/`. The framing notebook reads it from there.
3. `data-cleanup.ipynb` reads the copy of the same data that the programme hosted in 2022, and writes `data/cleaned_sales_data.csv`. If that link stops working, point `data_url` at your local file.
4. Open `tata-data-viz.twb` in Tableau Desktop. When it asks for the data source, point it at your copy of `Online Retail.xlsx`.

Outputs that printed rows of the data have been cleared from the saved notebooks. The counts and charts are kept.

## What is not in this repo

I left out everything that was not my own work. That covers the Forage task briefs, the retail data, the sample solution workbook and the sample questions that came with the programme. The last module was a recorded presentation, which I did not keep.

## Data and licence

The Online Retail data set is by Chen, Sain and Guo (2012) and is published by the UCI Machine Learning Repository under CC BY 4.0. Please download it from the source.

My code and writing in this repo are under the [MIT licence](LICENSE). The licence does not cover the data, the Forage briefs or any Tata material, and none of those are included here.
