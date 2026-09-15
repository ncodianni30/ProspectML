# ProspectML

## Minor League to MLB Hitter Projection

ProspectML is a baseball analytics project exploring how Minor League hitter performance can be used to project MLB offensive ability.

The project uses Minor League hitting statistics to predict several MLB offensive outcomes and combines those predictions into a composite **Hitting Ability Score (HAS)**.

## Project Questions

* How well can Minor League performance predict MLB offensive production?
* Which Minor League statistics provide the most useful information for projecting MLB performance?
* Which MLB offensive components are most predictable?
* Where does the model perform well, and where does it struggle?

## Data

The project combines Minor League and MLB hitting statistics and organizes player performance across different Minor League levels, including High-A, Double-A, and Triple-A.

The final dataset contains **936 players** who met the project's MLB playing-time criteria.

## Methodology

The project includes:

* Player-level data cleaning and matching
* Minor League performance aggregation
* Feature engineering
* MLB outcome construction
* Multiple machine-learning models
* Model comparison using MAE, RMSE, and R²
* Feature importance analysis
* Component-based prediction of MLB offensive outcomes

## Hitting Ability Score

The Hitting Ability Score combines four MLB offensive components:

* wOBA — 35%
* wRC+ — 35%
* OBP — 15%
* ISO — 15%

This composite score provides a broader measure of offensive ability than relying on a single statistic.

## Model Development

Several approaches were tested, including:

* Baseline Mean
* Linear Regression
* Ridge Regression
* Random Forest
* Tuned Random Forest
* XGBoost
* Extra Trees

The final approach used a **component-based Extra Trees model**, which predicted individual MLB offensive components before combining those predictions into the final Hitting Ability Score.

The component-based Extra Trees model produced the strongest overall validation performance, although its results were broadly comparable to Ridge Regression and other top-performing approaches.

## Key Findings

The analysis found that Minor League performance contains meaningful information about future MLB offensive performance, but statistical performance alone does not completely explain MLB outcomes.

The model performed substantially better on typical players than on extreme outcomes. This highlights the difficulty of predicting unusually high or low MLB offensive performance from Minor League statistics alone.

Career-level Minor League statistics were among the strongest sources of predictive information, suggesting that larger and more stable samples can provide useful signal for projection.

## Limitations

The current project only includes players who ultimately reached MLB, creating potential **survivorship bias**.

The model also does not currently incorporate information such as:

* Scouting grades
* Physical measurements
* Player development trends
* Broader organizational or environmental context

As a result, ProspectML should be viewed as a decision-support tool rather than a replacement for scouting or player evaluation.

## Future Development

Future versions of ProspectML could:

* Incorporate standardized scouting grades
* Add physical and athletic measurements
* Include development trends and age-relative performance
* Include players who did not reach MLB
* Test alternative or learned Hitting Ability Score weights
* Investigate where statistical projections disagree with scouting evaluations

## Project Files

### `notebooks/`

Contains the project's analysis workflow:

1. **01-Data_Prep** — Data cleaning, matching, and preparation
2. **02-Exploratory_Analysis_&_Feature_Selection** — Exploratory analysis and predictor selection
3. **03-Hitter_Ability_Score_Construction** — Construction of the MLB Hitting Ability Score
4. **04-ProspectML_Model** — Model development, comparison, and evaluation
5. **05-Concluding_Analysis** — Final analysis, player-level results, and limitations

### `ProspectML_Report.docx`

Full written report documenting the project, methodology, findings, and implications.

## Conclusion

ProspectML demonstrates how statistical analysis and machine learning can be applied to baseball player evaluation. The project combines baseball knowledge with data preparation, predictive modeling, model evaluation, and practical interpretation to investigate the relationship between Minor League performance and MLB offensive production.

