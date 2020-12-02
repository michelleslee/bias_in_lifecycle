# Bias in Model Development Lifecycle Questionnaire

**Project Title**: Bias in model development lifecycle questionnaire 

**Lead researcher**: Michelle Seng Ah Lee (sal87@cam.ac.uk) 

This questionnaire will go through an assessment to identify the potential biases in a model development lifecycle.
Think of a model that you would like to assess for potential unfair bias and discrimination.
Below are the biases and their definitions for your reference.

![alt text](https://github.com/michelleslee/bias_in_lifecycle/blob/master/lifecyclebias.png?raw=true)

![alt text](https://github.com/michelleslee/bias_in_lifecycle/blob/master/biasdefinitions.png?raw=true)

## A. KEI KRI design
 - [ ] **A.1 Model description**: Describe a model you would like to assess for potential unfair and discriminatory bias. Ex) a supervised machine learning model to predict whether a mortgage loan will default
 - [ ] **A.2 Positive impact: overall**: What positive impact can this model have on the target population? Ex) predicting default risk can help prevent unaffordable loans being approved 
 - [ ] **A.3 Positive impact: performance**: What is the benefit of higher accuracy / precision for the target population? Ex) better credit risk evaluation model leads to greater financial inclusion, better hiring algorithm leads to overall higher employee performance / reduction in attrition
 - [ ] **A.4 Positive impact: operationalisation**: Can these objectives be measured and quantified? If yes, list how they can be formalised. Ex) unaffordable loan approval can be measured based on false negative rate (i.e. loans predicted to be repaid but defaulted), and greater financial inclusion can be measured as the total amount of loans given out 
 - [ ] **A.5 Negative impact: allocative harm**: What are any potential allocative harms (withholding of opportunities / resources)? Ex) model may be more likely to give loans to certain groups, e.g. race and gender, which would replicate and widen the societal inequalities 
 - [ ] **A.6 Negative impact: representational harm**: Is there any representational harm (diminished identity)? Ex) for an image search algorithm for “CEO”, returning more men than women reinforces the bias in identity 
 - [ ] **A.7 Negative impact: representational harm operationalisation**: Is there any representational harm (diminished identity)? Ex) for an image search algorithm for “CEO”, returning more men than women reinforces the bias in identity
 - [ ] **A.8 Negative impact: fundamental rights**: Are there any fundamental rights at stake? Ex) right to self-determination, liberty, due process of law, freedom of movement, privacy, freedom of thought, freedom of religion, freedom of expression, right of peaceful assembly, right to freedom of association
 - [ ] **A.9 Negative impact: operationalisation**: Can these objectives be measured and quantified? If yes, list how they can be formalised. Ex) unaffordable loan approval can be measured based on false negative rate (i.e. loans predicted to be repaid but defaulted), and greater financial inclusion can be measured as the total amount of loans given out  
 
## B. Design: historical/external bias
 - [ ] **B.1 History of discrimination**: Is there documented historical discrimination in the domain area against a protected class, as defined in the UK Equality Act? Ex) academic studies demonstrate lower mortgage approval rates for racial minorities in the US, especially black and Hispanic applicants. 
    - [ ] age 
    - [ ] disability 
    - [ ] gender reassignment 
    - [ ] marriage or civil partnership (in employment only) 
    - [ ] pregnancy and maternity 
    - [ ] race 
    - [ ] religion or belief 
    - [ ] sex 
    - [ ] sexual orientation 
    - [ ] other ______________________

 - [ ] **B.2 Acceptable vs. unacceptable inequalities**: For that group, select which of the following layers of inequality is a justifiable source of differences in outcome. The justification may include 1) well-founded causal relationship to an outcome of interest (e.g. income to risk of default) and/or 2) a feature that is within the individual’s control and transparently disclosed (e.g. history of paying bills on time)
    - [ ] Disability 
    - [ ] Race 
    - [ ] Agge
    - [ ] National origin 
    - [ ] Socioeconomic status 
    - [ ] Talent/ education 
    - [ ] Personality traits 
    - [ ] Preferences 
    - [ ] Culture 
    - [ ] Discrimination in related markets 
    - [ ] Other ______________________
    
 - [ ] **B.3 Potential proxies**: Which of the features in your data may be associated with the unjustifiable sources of differences in outcome, e.g. postcode with race? 
 - [ ] **B.4 World as-is vs. ideal**: Is there any misalignment between the ground truth (world as-is) and the organisation’s values? For example, there may be more male senior executives, but the organisation’s objective is to have stronger female representation in leadership.

## C. Data collection: Representation bias
 - [ ] **C.1 Selection bias**: Is the marketing / targeting / data collection strategy returning a representative sample of the population? Ex) is the mortgage company advertised in majority-white neighborhoods? 
 - [ ] **C.2 Subjective recorded features**: Are any of the recorded features affected by human judgment? Ex) the data set may include the interviewer’s scores on the candidates’ performance
 - [ ] **C.3 Third party**: Are any of the recorded features produced by a third party data set or model? Ex) the credit scores may be provided by a specialist agency
 - [ ] **C.4 Known unknown**: Is the ground truth of actual outcomes known? Ex) whether denied loans would have defaulted is unknown
 - [ ] **C.5 Sample size**: Is there sufficient sample in each subgroup of interest for this analysis? Ex) only 5% of applicants are Native Americans

## D. Feature engineering: measurement bias
 - [ ] **D.1 Different measurements**: Are there differences in the measurement process between groups for either input features or the target outcome? Ex) high-minority neighborhoods are more frequently patrolled, leading to higher arrest rates
 - [ ] **D.2 Different data quality**: Are there differences in the data quality between groups? Ex) schools in poor districts have lower quality recorded data on student performance
 - [ ] **D.3 Subjective engineered features**: 3.	Are there any features added by the model developer that could it be affected by his/her judgment? Ex) the data scientist added flags of what he/she considers an important feature from a job applicant’s CV, e.g. “participated in university extracurricular activities” or “held a leadership position”
 - [ ] **D.4 Test for proxies**: Are there proxies of outcome that may be also proxies of a protected group membership, especially those with a history of discrimination in this domain area? Ex) In US mortgage lending, employees were more likely to recommend loan types that are expensive to finance to black and Hispanic applicants, which would affect their recorded loan type.
 - [ ] **D.5 Measurement accuracy**: Does the measurement closely match what the model intends to track? Ex) arrest ≠ crime rate, final grades ≠ student success

## E. Model build and training: aggregation bias
 - [ ] **E.1 Heterogeneous groups**: Are the populations heterogeneous in a way that a single model cannot account for all subgroups? (See: Simpson’s paradox) Ex) Medical diagnosis algorithm should be different for men and women given their different body compositions 
 - [ ] **E.2 Heterogeneous mechanisms**: Are there other heterogeneous mechanisms in play that are being inaccurately aggregated that may be associated with protected features? Ex) differences in behavior across products, different time periods, different data sets, etc.
 - [ ] **E.3 Sub-group performance**: Have you tested model performance on all protected subgroup combinations? Ex) the model has similar error rates for men and women and for black and white applicants, but it has high error rates for black women
 
## F. Model evaluation: evaluation bias
 - [ ] **F.1 Trade-offs**: Are all trade-offs on objectives identified for all available models? All objectives should be quantified into metrics where possible to enable model comparison Ex) mapped the trade-off between financial inclusion and minority race denial rates for mortgage lending for 10 versions of predictive models
 - [ ] **F.2 Objective coverage**: Do the metrics cover all measurable objectives related to positive and negative impacts on the target population? Ex) The assessment of mortgage default prediction algorithm covers unaffordable loans (false positive), financial inclusion, minority race denial rate. It also includes qualitative assessment of explainability.
 - [ ] **F.3 Metric alignment with values**: Do your metrics align with the relative importance of False Positives vs. False Negatives? Ex) those predicted to repay but defaulted represent unaffordable loans / cost to the company, and those predicted to default but would have repaid represent missed opportunity / allocative harm
 - [ ] **F.4 Metric over-fitting**: Is there a metric the model may be over-fitting to? Ex) the main credit risk evaluation accuracy metric
 - [ ] **F.5 Sub-group performance disparity**: Are there any disparities in sub-group performance? Ex) Does the model have more errors among women than men?
 - [ ] **F.6 Confidence**: Are confidence intervals acceptable and understood? Ex) Especially if a sub-group population is under-represented, they may have a larger confidence interval around their predictions
 
## G. Model productionisation and monitoring: deployment bias
 - [ ] **G.1 System**: Is the model a part of a complex sociotechnical system, e.g. inter-connected models or embedded in human processes? Ex) A CV-scoring algorithm may feed into a candidate’s evaluation system
 - [ ] **G.2 Feedback**: Is there an appropriate human feedback mechanism for any errors? Ex) A human reviewer reads a sample of machine transcriptions to identify any errors and retrains the algorithm with the corrections
 - [ ] **G.3 Robustness to external changes**: Is the model robust to any external changes, e.g. shifts in policy, dramatic changes in input data, etc.? Ex) There is a monitoring mechanism in place to alert the team if there is a significant change in the distribution in the input data beyond a pre-defined threshold 
 - [ ] **G.4 Bias reinforcement**: Can the feedback loop be reinforcing any existing biases? Ex) if loans predicted to default are denied. Is there any user interaction with the output? Ex) user clicking on links recommended by the algorithm
 
*Contact: sal87@cam.ac.uk*
