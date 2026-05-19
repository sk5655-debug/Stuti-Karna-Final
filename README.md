# Childhood Trauma and Women's Mental Health

# Data Analysis Plan

In the present analysis, childhood trauma exposure will be examined as the primary independent variable (IV), and five adult mental health outcomes will serve as dependent variables (DV): depression diagnosis, substance use, depressed affect score, sense of personal control, and psychological autonomy. 

Childhood trauma is based on the composite abuse score (A1SEMAPA), a continuous scale which has been derived from 15 items assessing maternal and paternal physical, emotional, and sexual abuse during childhood (1 = a lot, 4 = not at all). Respondents scoring below 3 are classified as the Trauma group, and those scoring 3 or above as the No Trauma group. 

First, the full sample will beb used to compare men and women on depression and substance use rates, establishing the gender gap that motivates the focus on women. Then the sample will be filtered to women only for all subsequent analyses. Group differences between Trauma and No Trauma group will be assessed using Welch's independent samples t-tests, with Cohen's d as a measure of effect size. 

Correlations will be computed between the childhood abuse score and each outcome variable, as well as key socioeconomic variables (income, education), since the outcomes include both binary and ordinal measures Spearman's rho will be more appropriate than Pearson's r. 

To evaluate whether the association between childhood trauma and adult mental health persists after accounting for socioeconomic factors, we will use a regression model separately for each outcome. For binary outcomes such as depression diagnosis and substance use Logistic regression will be used and for continuous outcomes (depressed affect score, sense of control, personal mastery, and autonomy) ordinary least squares (OLS) regression will be used. Each outcome will be modelled twice: first with abuse score as the sole predictor (Model 1), and then with income, education, and age added as covariates (Model 2).

## Dataset & Population
Midlife in the United States (MIDUS 1), 1994–1995

Source: Inter-university Consortium for Political and Social Research (ICPSR), Study No. 2760

URL: https://www.icpsr.umich.edu/web/NACDA/studies/2760

Citation: Brim, O. G., Ryff, C. D., & Kessler, R. C. (2004). *Midlife in the United States (MIDUS 1), 1994–1995*. ICPSR02760-v19. Ann Arbor, MI: Inter-university Consortium for Political and Social Research.
Sample size: N = 7,108 respondents

The MIDUS 1 is a nationally representative survey of US adults aged 25–74 covering physical health, mental health, and life experiences including childhood adversity. The data has been de-identified.

# Research Questions:
## Primary: 
Do women with a history of childhood abuse show higher rates of depression, substance use, and lower sense of control and autonomy compared to women with no such history?
## Secondary: 
Does childhood trauma predict these outcomes above and beyond what is explained by income, education, and age?

## Variable Construction
Education APPB1 has been callapsed to 4 groups. Income A1SHHTOT has been log-transformed. Depression A1PDEPDX is the depression diagnosis and dep_score A1PDEPAF is depressed affect; higher = more depressed. Abuse_score A1SEMAPA is the combined maternal and paternal abuse composite score; lower=more abuse. Trauma group has been created using abuse_scores; if <3 Trauma, if >3 No Trauma.

## Dependencies
to run this code you need Python (version 3.9 or higher). 
pandas: For creating datsets and handling data. numpy: For calculations. seaborn: for statistical visualization. matplotlib:	for plotting graphs. scipy.stats	To run statistical tests. statsmodels: for	statistical modeling/regression.

# How to Run the Analysis
### Step 1. Data cleaning & descriptives
 Load dataset from GitHub. Recode diagnosis variables from SPSS coding (1=yes, 2=no) to binary (1/0). Replace refused and don't know codes with NaN. Log-transform household income to correct for positive skew. (Section 1-2)
### Step 2: Comparing Men vs Women
Compare men and women on depression and substance use rates using the full sample (N = 7,108).(Section 3-4)
### Step 3: Filtering for only women and cleaning the data
Retain sample of only female respondents (N = 3,666). (Section 5-6). Need to run this filtering section code in order for everything else to work. Otherwise, we need to start again from section 1.
### Step 4. Childhood Trauma Group Variable
Use the MIDUS composite childhood abuse score (A1SEMAPA) to create a binary trauma group variable. (Section 7)
### Step 5. Descriptive Statistics
Regroup Data. Examine distributions of income, depression scores, education, and age. Compare depression and substance use rates between the two groups.(Section 8-9)
### Step 6. Group Comparison
Use a Welch's t-test to compare depressed affect scores between the Trauma and No Trauma groups. (Section 10-13)
### Step 7. Correlation Analysis
Run Spearman correlations between the abuse score, depression, substance use, income, and education.(Section 14)
### Step 8. Regression Models
Run unadjusted (Model 1) and adjusted (Model 2) regression models for each outcome separately, using logistic regression for binary outcomes and OLS for continuous outcomes. Visualize with Odds Ratio Plot. (Section 15-16)

## Key Finding
Childhood trauma exposure was significantly associated with higher rates of depression and substance use problems, and with lower sense of control, personal mastery, and psychological autonomy in adult women. These associations persisted after controlling for income, education, and age across all five outcomes, indicating that the long-term impact of childhood abuse on mental health and psychological resources is not reducible to socioeconomic disadvantage alone.

# Results:
## Descriptive statistics:
<img width="497" height="535" alt="5" src="https://github.com/user-attachments/assets/eff1947a-4aed-4ed5-b479-9738c7d072bb" />

The analysis sample included 3,666 women with a mean age of 46.6 years (SD = 13.1, range 20–75). Education: 49.7% HS diploma/GED, 25.7% college degree or higher, 13.0% some college, 11.4% less than HS, 0.2% missing. Median household income was $48,000 (mean = $67,887, SD = $61,445, N = 3,087 with valid income data). Overall depression rate was 16.0% and substance use problem rate was 1.5%.

<img width="606" height="109" alt="4" src="https://github.com/user-attachments/assets/9fe806b5-f795-458c-8179-addf9deb6890" />

Of the 3,666 women, 1,684 (45.9%) were classified as the Trauma group and 1,625 (44.3%) as the No Trauma group; 345 were excluded due to missing abuse data. 57.5% of women (N = 2,108) reported high abuse scores on at least one item. Sense of control (M = 5.42, SD = 1.06), personal mastery (M = 5.78, SD = 1.04), and autonomy (M = 16.26, SD = 3.44) were assessed across 3,294 women with valid data.

<img width="642" height="257" alt="6" src="https://github.com/user-attachments/assets/9935ff5e-11aa-4837-ad5a-a739a1f32e15" />

Gender Comparison (Full Sample N = 7,108):

Women showed significantly higher depression rates than men (16.0% vs 10.3%). Men showed higher substance use problem rates (3.7% vs 1.5%). A Welch's t-test confirmed that depressed affect scores were significantly higher in women than men (t = −8.452, p < 0.001, Cohen's d = −0.20).

<img width="501" height="95" alt="1" src="https://github.com/user-attachments/assets/65afc49e-10b9-4ef5-892c-febb612558fe" />
<img width="616" height="25" alt="2" src="https://github.com/user-attachments/assets/3b6c9764-134b-4c7b-9399-1a205012a18d" />
<img width="608" height="300" alt="3" src="https://github.com/user-attachments/assets/49547da7-7162-4c79-ab08-39f1de54dd2d" />

## Group Comparison (Trauma vs No Trauma)
All five outcomes differed significantly between groups. Women with a trauma history showed higher depression scores and substance use rates, and lower sense of control, mastery, and autonomy.

<img width="1389" height="887" alt="7" src="https://github.com/user-attachments/assets/d8ab1eea-ee70-4b26-bc58-ea02d7e33dca" />

In the depressed affect score: the Trauma group is nearly double the No Trauma bar group.
<img width="609" height="439" alt="8" src="https://github.com/user-attachments/assets/deeffc42-f9e3-4b48-9b2e-458879e47a0a" />

The wide base at 0 in both groups means that most women in both groups reported no depressive symptoms — which is expected in a non-clinical sample. However, the Trauma group has a noticeably wider and fuller body from scores 1–4, meaning more women in that group are scoring in the mild-to-moderate range. The thin tail reaching 7 exists in both groups but is slightly more pronounced in the Trauma group, representing the small proportion with high depressive symptom counts.

<img width="1389" height="495" alt="9" src="https://github.com/user-attachments/assets/de206307-399c-414a-8257-77cf59fbea84" />

Sense of Control: both groups are centred high but the Trauma group has a longer lower tail, stretching down toward 1–2. The No Trauma group is more tightly packed in the upper range. Trauma doesn't make everyone feel out of control, but it does produce a subset of women who feel very low control.
Personal Mastery has a very similar pattern to control, even though the difference between the two groups is slightly smaller. Both groups peak around 5–6, but the Trauma group again has more mass in the lower scores.
Autonomy: Both groups have a similar overall shape, but the No Trauma group's median is higher.

## Correlation Analysis (N = 3,046)
All correlations use Spearman's rho.

<img width="646" height="157" alt="10" src="https://github.com/user-attachments/assets/628a73a6-ff9f-4044-8438-64241ef5576e" />

Negative correlations for depression and substance use indicate that more childhood abuse was associated with greater likelihood of both outcomes. The positive correlations with sense of control, mastery, and autonomy suggest that women who experienced more abuse reported weaker psychological resources, though all effect sizes were small (r = 0.06–0.18). Income and education showed similar small negative associations with depression, meaning lower socioeconomic status was linked to higher depression rates, consistent with the broader literature.
*since abuse_score is coded where lower = more abuse, every correlation's direction is flipped.

## Relationship between SES and childhood trauma
A pattern emerged across the regression models: income predicted sense of control and substance use but not autonomy, while education predicted autonomy and depression but not substance use or mastery. This suggests that different socioeconomic resources may protect different dimensions of wellbeing, and that childhood trauma operates as an independent risk factor above and beyond these protective factors.

## Regression Models
Depression
<img width="642" height="304" alt="11  dep" src="https://github.com/user-attachments/assets/f04df213-d2b0-4920-ba84-d89280f99088" />

Model 1 (unadjusted):
OR = 0.524, p < 0.001***. 
Model 2 (adjusted):
The effect of childhood trauma on depression persisted after controlling for all covariates.

Substance Use

<img width="631" height="260" alt="12  substance" src="https://github.com/user-attachments/assets/de6d939c-faa4-498e-a3d9-19b77f404f89" />

Model 1 (unadjusted): OR = 0.447, p < 0.001***. 
Model 2 (adjusted): abuse_score OR = 0.473 (p < 0.001***), log_income OR = 0.640 (p < 0.001***), education OR = 1.034 (ns), age OR = 0.969 (p < 0.05*). Education did not predict substance use after adjustment, but income and age did.

Sense of Control
<img width="641" height="260" alt="13  control" src="https://github.com/user-attachments/assets/235bf947-5fbe-416b-9718-4dff9ebec287" />

Model 1: β = 0.286, p < 0.001***. 
Model 2 (adjusted): abuse_score β = 0.279 (p < 0.001***), log_income β = 0.128 (p < 0.001***), education β = 0.057 (p < 0.001***), age β = −0.008 (p < 0.001***). All predictors were significant.

Personal Mastery
<img width="641" height="260" alt="14  mastery " src="https://github.com/user-attachments/assets/13857d36-8fa7-40c7-a42c-000e0b82e1bc" />

Model 1: β = 0.233, p < 0.001***. 
Model 2 (adjusted): abuse_score β = 0.233 (p < 0.001***), log_income β = 0.050 (p < 0.05*), education β = 0.014 (ns), age β = −0.005 (p < 0.01**). Education did not predict mastery after adjustment.

Autonomy
<img width="641" height="260" alt="15  autonomy" src="https://github.com/user-attachments/assets/007e2d0a-622a-4254-bba7-31f5034c1cd2" />

Model 1: β = 0.576, p < 0.001***. 
Model 2 (adjusted): abuse_score β = 0.523 (p < 0.001***), log_income β = 0.039 (ns), education β = 0.069 (p < 0.05*), age β = 0.035 (p < 0.001***). Income did not predict autonomy after adjustment, but education and age did.

<img width="1990" height="495" alt="16" src="https://github.com/user-attachments/assets/012ba0e5-f3d7-4d49-9780-5ce8ab4cd7f6" />

### Depression and Substance Use
For every one unit increase in abuse score (i.e. less abuse), the odds of depression dropped by ~46%. Conversely, more abuse had significantly higher odds of depression and substance use problems, even after controlling for everything else. 
Education had a small but significant protective effect on depression and older women in this sample had slightly lower odds of depression and substance use.
Income was a stronger protective factor for substance use than for depression.

### Sense of Control, Mastery, Autonomy
Higher abuse score (less abuse) predicted significantly more control, mastery, and autonomy. Trauma erodes all three psychological resources
Income predicted control and mastery but barely predicted autonomy.
Education predicted autonomy and control but not mastery.
Age was slightly negative for control and mastery (older women feel slightly less in control), but positive for autonomy (older women feel more autonomous).

Results are in support of the primary research question that childhood trauma does seem to predict worse adult mental health and lower psychological resources in women, independently of socioeconomic status.
The secondary finding worth highlighting is the income vs education dissociation: income protected against substance use and sense of control, while education protected against depression and autonomy — suggesting different psychological pathways.
