# hedgingAsPolitenessStrategy

The hedgingAsPolitenessStrategy project uses Reddit AITA text corpus data and identifies statistically significant differences in the usage of hedging words in terms of age and gender. 

## Basic Idea

This project uses Python libraries including Pandas, NumPy, spaCy, and Statsmodels to identify statistically significant differences in the usage of different categories of hedging words in terms of age and gender.

### Hedging Words Primer

Hedging words can be divided into various categories, including: 

- Plausibility Shields: Words that express uncertainty.
- Adaptors: Words that modify the truthfulness of a given statement. 


### Stimuli Examples

| Plausibility Shields | Adaptors |
| -------------------- | -------- |
| <b>I think</b> it was okay. | It was <b>kind of</b> good.|
| <b>I guess</b> it was alright. | The store was <b>sort of</b> nearby.|

## Research Goals 

This project examined whether there were categorical differences in the usage of hedging words (as a proxy for politeness strategy) in terms of age and gender. 
>If this is the case, we expect that there would be statistically significant differences in terms of age and gender in (a) the usage frequency of Plausibility shields and (b) the usage frequency of Adaptors.

## Implementation

Text extraction and preliminary pre-processing of Reddit AITA corpus data were completed using NumPy, Pandas, and spaCy 
>See finalprojectDataExtract.ipynb

Statistical analyses of corpus data were completed using StatsModels 
>See finalProjectDataProcessing.ipynb

## Results & Interpretation 

### Plausibility Shield Usage

|           | Estimate | Std. Error | Z-Value | P-Value |
| --------- | -------- | ---------- | ------- | ------- |
| Intercept | -1.1843 | 0.011 | -103.983 | < 0.001 |
| gender[m] | -0.0904 | 0.019 | -4.703 | < 0.001 |
| age | 0.0004 | 0.002 | 0.246 | 0.805 |
| age:gender[m] | 0.0037 | 0.003 | 1.422 | 0.155 |

Table 1. Plausibility Distribution by Age & Gender

- Table 1 indicates that female speakers use Plausibility Shields more frequently than male speakers in text (p < 0.001, z = -4.703). There is also no significant effect of age or of the interaction between age and gender.

### Adaptor Usage

|           | Estimate | Std. Error | Z-Value | P-Value |
| --------- | -------- | ---------- | ------- | ------- |
| Intercept | -0.9627 | 0.011 | -89.063 | < 0.001 |
| gender[m] | -0.0861 | 0.018 | -4.742 | < 0.001 |
| age | -0.0141 | 0.002 | -7.989 | < 0.001 |
| age:gender[m] | 0.0093 | 0.003 | 3.668 | < 0.001 |

Table 2. Adaptor Distribution by Age & Gender

- Table 2 indicates that female speakers use Adaptors more frequently than male speakers in text (p < 0.001, z = -4.742). There is also a significant effect of age and an interaction between age and gender.

## Conclusion

Hypotheses (a) and (b) are mostly upheld. There is a statistically significant difference in terms of gender in the usage of Plausibility Shields and Adaptors. However, when looking at differences in terms of age, there is a difference in the usage of Adaptors but not Plausibility Shields.

## Selected References

Beekhuizen, B. (2026).  P4: Variant detection. [Jupyter Notebook]. https://q.utoronto.ca/courses/421331.

Prince, E. F., Frader, J., & Bosk, C. (1980). On Hedging in Physician-Physician Discourse. https://www.scribd.com/document/477663953/Prince-Hedging

Speelman, D. (2014). Logistic Regression: A Confirmatory Technique for Comparisons in Corpus Linguistics. In <i>(eds. Glynn, D., & Robinson, J. A.) Corpus Methods for Semantics.</i> John Benjamins Publishing Company, Amsterdam. https://benjamins.com/catalog/hcp.43.18spe

Tanj, J. (2013). Pragmatic Functions of Hedges and Politeness Principles. International Journal of Applied Linguistics & English Literature ISSN 2200-3592 (Print) ISSN 2200-3452 (Online), 2(4):155–160. https://www.researchgate.net/publication/272991102_Pragmatic_Functions_of_Hedges_and_Politeness_Principles.
