# Credit Card Analysis

An exploratory data analysis project investigating which behavioural and account-usage factors are associated with credit card customer churn, testing four hypotheses across three charting libraries.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

## Dataset Content

The dataset is the BankChurners and it contains 10,127 credit card customer records which include: Account details, Credit limit, Transaction activity, Inactivity, Etc. It is a synthetic dataset from Kaggle. 
Here is the link for the dataset: https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers

## Business Requirements

To understand which behavioural and usage patterns are associated with customer churn, in order to identify early warning signs and highlight which factors are, and are not, meaningful predictors.

## Hypothesis and how to validate?

H1: Customers who churn with high utilization and short tenure show a "bust-out" pattern. Validated with a boxplot, scatter plot, and interactive scatter plot of utilization, tenure, and revolving balance by attrition status.

H2: A mismatch between transaction amount change and count change is more common among churned accounts. Validated with a histogram, boxplot, and interactive scatter plot of an engineered mismatch ratio.

H3: Churned customers carry higher utilization, especially those with fewer bank products. Validated with a bar chart, grouped boxplot, and interactive heatmap of utilization by relationship count and attrition status.

H4: More frequent bank contact is associated with higher churn. Validated with a bar chart, seaborn bar plot with confidence intervals, and interactive bar chart of churn rate by contact frequency.

## Project Plan

Data collection and set up: The dataset was sourced from Kaggle, downloaded and saved to the raw data folder. The dataset was explored by checking the columns, value counts, statistics, missing values and duplicates. Necessary cleaning was then carried out, including handling Unknown values, outliers, data leakage columns and feature engineering. The cleaned data was saved as an intermediate CSV file.

Data Visualisation: The cleaned dataset was analysed using scatter plots, boxplots, histograms, line graphs and bar charts. Different visualisations were selected based on the variables and hypotheses being investigated. Matplotlib, Seaborn and Plotly were used to identify and communicate relevant patterns in the data.

## The rationale to map the business requirements to the Data Visualisations

Bust-out pattern (H1): boxplot for overall spread, scatter plot to check for the specific short-tenure/high-utilization clustering predicted, interactive version for point-level inspection.

Spend/count mismatch (H2): histogram for the mismatch ratio's shape, boxplot to compare it by attrition status, scatter plot to check whether churned customers sat off the diagonal or simply showed lower overall activity.

Utilization by relationship depth (H3): bar chart for the headline comparison, boxplot to break it down by relationship count, heatmap for a clear view of the interaction.

Contact frequency (H4): all three charts compared churn rate by contact count; Seaborn added confidence intervals to flag where sample size mattered; Plotly's hover data showed exact customer counts per group.

## Analysis techniques used

Boxplots, scatter plots, histograms, bar charts, and an interactive heatmap, matched to each hypothesis's variable types.

Feature engineering was required for H2 (an amount/count ratio), including an infinite-value check before plotting, since a zero denominator in a few rows made the ratio unplottable.

H3 was not supported by the data — the opposite pattern was found — and this is reported as-is rather than adjusted to fit the prediction.



## Ethical considerations (optional)

The dataset contains no real, identifiable individuals, so poses no direct privacy risk. It does represent real financial behaviour, so similar analysis applied in a live setting (e.g. flagging customers for review) would need appropriate oversight — not a concern this project itself involves, but worth noting.
## Use of AI

I used Claude (Anthropic) to suggest appropriate graphs for visualisations
I used Claude (Anthropic) to help debug code and understand errors
I used Claude (Anthropic) to help refine the markdown commentary

## Unfixed Bugs

None remaining. Bugs encountered and resolved during development are documented below.

Regular calls with a peer helped greatly throughout the assignment.

## Development Roadmap

Challenges: working-directory drift from re-running a relative os.chdir() without a kernel restart; a leftover empty try: block causing an IndentationError; a missing nbformat package blocking Plotly rendering; infinite values in an engineered ratio column; one hypothesis contradicting its prediction.

Strategies: reading full tracebacks rather than the last line only; a consistent Restart Kernel → Run All habit; using AI tools to debug and sanity-check interpretations.

Next steps: statistical significance testing alongside visual findings; a predictive churn model; interactive dashboard tools.


## Main Data Analysis Libraries

Pandas — cleaning and grouping, e.g. df_clean.groupby('Attrition_Flag')['Avg_Utilization_Ratio'].mean().

NumPy — identifying/filtering infinite values in the engineered ratio column.

Matplotlib — baseline chart per hypothesis, e.g. df_clean.boxplot(column='Avg_Utilization_Ratio', by='Attrition_Flag').

Seaborn — deeper comparison per hypothesis, e.g. sns.boxplot(data=df_clean, x='Total_Relationship_Count', y='Avg_Utilization_Ratio', hue='Attrition_Flag').

Plotly — interactive chart per hypothesis, e.g. px.imshow() for the utilization/relationship-count heatmap.

## Credits

The dataset used is the Credit Card Customers dataset from Kaggle.
https://plotly.com/python/ - Plotly documentation
https://seaborn.pydata.org/ - Seaborn documentation

