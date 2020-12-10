# Bias in Model Development Lifecycle Questionnaire

**Project Title**: Bias in model development lifecycle questionnaire 

**Lead researcher**: Michelle Seng Ah Lee (sal87@cam.ac.uk) 

This questionnaire will go through an assessment to identify the potential biases in a model development lifecycle.
Think of a model that you would like to assess for potential unfair bias and discrimination.
Below are the biases and their definitions for your reference.

![alt text](https://github.com/michelleslee/bias_in_lifecycle/blob/master/lifecyclebias.png?raw=true)

![alt text](https://github.com/michelleslee/bias_in_lifecycle/blob/master/biasdefinitions.png?raw=true)

## A. Background information
 - [ ] **A.1 Model description**: Describe a model you would like to assess for potential unfair and discriminatory bias. Ex) a supervised machine learning model to predict whether a mortgage loan will default
 - [ ] **A.2 Positive impact: overall**: What positive impact can this model have on the target population? This may include an explicit social impact as intended by the model (e.g. building a computer vision model to read sign language to increase service accessibility), or it could be associated with the efficiency of the business and market that trickles down into a positive result for the consumers, e.g. more precisely predicting default risk can help prevent unaffordable loans being approved.
 - [ ] **A.3 Positive impact: performance**: What is the benefit of higher accuracy / precision for the target population? Ex) better credit risk evaluation model leads to greater financial inclusion, better hiring algorithm leads to overall higher employee performance / reduction in attrition
 - [ ] **A.4 Positive impact: operationalisation**: Can these objectives be measured and quantified? If yes, list how they can be formalised. Ex) unaffordable loan approval can be measured based on false negative rate (i.e. loans predicted to be repaid but defaulted), and greater financial inclusion can be measured as the total amount of loans given out 
 - [ ] **A.5 Negative impact: allocative harm**: What are any potential allocative harms (withholding of opportunities / resources)? Ex) model may be more likely to give loans to certain groups, e.g. race and gender, which would replicate and widen the societal inequalities 
 - [ ] **A.6 Negative impact: representational harm**: Is there any representational harm (diminished identity)? Ex) for an image search algorithm for “CEO”, returning more men than women reinforces the bias in identity 
 - [ ] **A.7 Negative impact: representational harm operationalisation**: Is there any representational harm (diminished identity)? Ex) for an image search algorithm for “CEO”, returning more men than women reinforces the bias in identity
 - [ ] **A.8 Negative impact: fundamental rights**: Are there any fundamental rights at stake? Ex) right to self-determination, liberty, due process of law, freedom of movement, privacy, freedom of thought, freedom of religion, freedom of expression, right of peaceful assembly, right to freedom of association
 - [ ] **A.9 Negative impact: operationalisation**: Can these objectives be measured and quantified? If yes, list how they can be formalised. Ex) unaffordable loan approval can be measured based on false negative rate (i.e. loans predicted to be repaid but defaulted), and greater financial inclusion can be measured as the total amount of loans given out  
 
 Based on the answers above, think critically about the model's practical and ethical objectives, and when they may be in conflict with one another, understanding the prioritisation of and trade-offs between these objectives. 
 
 Below questions will align to each stage of the model development lifecycle. Answering yes indicates a risk that must be addressed, mitigated, and/or justified. 

## B. Design: historical/external bias
 - [ ] **B.1 History of discrimination**: Is there documented historical discrimination in the domain area against a protected class, as defined in the UK Equality Act? Ex) academic studies demonstrate lower mortgage approval rates for racial minorities in the US, especially black and Hispanic applicants. These are sub-groups to which special attention must be paid in testing for impact of the model.
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

 - [ ] **B.2 Acceptable vs. unacceptable inequalities**: For that group, select which of the following layers of inequality is a justifiable source of differences in outcome. For example, race and gender may be relevant to differential medical diagnoses, and talent / education may be relevant to recruiting and hiring algorithms. Is there any disagreement among relevant stakeholders?
    - [ ] Disability 
    - [ ] Race 
    - [ ] Age
    - [ ] National origin 
    - [ ] Socioeconomic status 
    - [ ] Talent/ education 
    - [ ] Personality traits 
    - [ ] Preferences 
    - [ ] Culture 
    - [ ] Discrimination in related markets (e.g. for a credit risk model, any inequality resulting from discrimination in the job market)
    - [ ] Other ______________________
    
 - [ ] **B.3 Potential proxies**: Identify the features in your data may be associated with the unjustifiable sources of differences in outcome, e.g. postcode with race or income with gender. Detailed tests would be undertaken in the feature engineering stage. Is there sufficient rationale for including these features, e.g. well-founded causal relationship to an outcome of interest (e.g. income to risk of default) or feature that is within the individual’s control and transparently disclosed (e.g. history of paying bills on time)?
 - [ ] **B.4 World as-is vs. ideal**: Is there any misalignment between the ground truth (world as-is) and the organisation’s values? For example, there may be more male senior executives, but the organisation’s objective is to have stronger female representation in leadership.

## C. Data collection: Representation bias
 - [ ] **C.1 Selection bias**: Is the marketing / targeting / data collection strategy returning a non-representative sample of the population? Ex) is the mortgage company advertised in majority-white neighborhoods, or is the recruiting firm only active at top universities? 
 - [ ] **C.2 Subjective recorded features**: Are any of the recorded features affected by human judgment? Ex) the data set may include the interviewer’s scores on the candidates’ performance
 - [ ] **C.3 Third party**: Are any of the recorded features produced by a third party data set or model? Ex) the credit scores may be provided by a specialist agency, or an open source data set on university rankings may be used in a hiring model
 - [ ] **C.4 Known unknown**: Is any ground truth of actual outcomes unknown? Ex) whether denied loans would have defaulted is unknown
 - [ ] **C.5 Sample size**: Is there insufficient sample in any subgroup of interest (especially those in B.1) for this analysis? Ex) only 1% of applicants are Native Americans

## D. Feature engineering: measurement bias
 - [ ] **D.1 Different measurements**: Are there differences in the measurement process between groups for either input features or the target outcome? Ex) high-minority neighborhoods are more frequently patrolled, leading to higher arrest rates
 - [ ] **D.2 Different data quality**: Are there differences in the data quality between groups? Ex) schools in poor districts have lower quality recorded data on student performance
 - [ ] **D.3 Subjective engineered features**: Are there any features added by the model developer that could it be affected by his/her judgment? Ex) the data scientist added flags of what he/she considers an important feature from a job application, e.g. “participated in university extracurricular activities” or “held a leadership position”
 - [ ] **D.4 Test for proxies**: Are there proxies of outcome that may be also proxies of a protected group membership, especially those with a history of discrimination in this domain area? Refer back to answers from B.3 on whether the inclusion of these proxies is justifiable. If the protected features are available, correlation tests are recommended. Ex) Job type and car value are associated with both auto insurance risk and gender. Car value may be justifiably included due to its causal relation to risk of accident-related claims, but job type may not be fully justifiable, e.g. if a male-dominated job titles, e.g. barbers, are charged different prices to female-dominated job title, e.g. hair stylists. The modeller may consider mitigating the gender bias by using a newly engineered feature more closely associated to the outcome of interest, e.g. typical amount of car usage in job, rather than directly using the job title.
 - [ ] **D.5 Measurement accuracy**: Is there any mis-match between the measurement and what the model intends to track? Ex) arrest ≠ crime rate, final grades ≠ student success

## E. Model build and training: aggregation bias
 - [ ] **E.1 Heterogeneous groups**: Are the populations heterogeneous in a way that a single model cannot account for all subgroups? (See: Simpson’s paradox) Ex) Medical diagnosis algorithm should be different for men and women given their different body compositions 
 - [ ] **E.2 Heterogeneous mechanisms**: Are there other heterogeneous mechanisms in play that are being inaccurately aggregated that may be associated with protected features? Ex) differences in behavior across products, different time periods, different data sets, etc.
 
## F. Model evaluation: evaluation bias
 - [ ] **F.1 Trade-offs**: Identify all trade-offs on objectives identified for all available models. All objectives should be quantified into metrics where possible to enable model comparison. Is there any tension between key objectives? Ex) mapped the trade-off between financial inclusion and minority race denial rates for mortgage lending for 10 versions of predictive models, but there is no obvious winner
 - [ ] **F.2 Objective coverage**: Are there any gaps in the metrics' coverage of all measurable objectives related to positive and negative impacts on the target population? Ex) The assessment of mortgage default prediction algorithm covers unaffordable loans (false positive), financial inclusion, minority race denial rate, but explainability should be qualitatively assessed
 - [ ] **F.3 Metric alignment with values**: Is there any mis-alignment of your model performances with the relative importance of False Positives vs. False Negatives? Ex) those predicted to repay but defaulted represent unaffordable loans / cost to the company, and those predicted to default but would have repaid represent missed opportunity / allocative harm
 - [ ] **F.4 Metric over-fitting**: Is there a metric the model may be over-fitting to? Ex) the main credit risk evaluation accuracy metric
 - [ ] **F.5 Sub-group performance disparity**: Is there any difference in model performance, measured on on all protected subgroups, especially those identified in B.1? Be sure to test all subgroup combinations, e.g. intersectional discrimination in race-gender. Ex) the model has similar error rates for men and women and for black and white applicants, but it has high error rates for black women
 - [ ] **F.6 Confidence**: Is there any barrier to the confidence intervals being accepted and understood by the relevant stakeholders? Ex) Especially if a sub-group population is under-represented, they may have a larger confidence interval around their predictions
 
## G. Model productionisation and monitoring: deployment bias
 - [ ] **G.1 System**: Is the model a part of a complex sociotechnical system, e.g. inter-connected models or embedded in human processes? Ex) A CV-scoring algorithm may feed into a candidate’s evaluation system, which should also be assessed holistically beyond the ML model
 - [ ] **G.2 Feedback**: Are there any gaps in the human feedback mechanism for any errors? Ex) A human reviewer reads a sample of machine transcriptions to identify any errors and retrains the algorithm with the corrections, but high-cost errors may be missed
 - [ ] **G.3 Robustness to external changes**: Test the model for robustness to any external changes, e.g. shifts in policy, dramatic changes in input data, etc. Are there any concerns on the organisation's ability to monitor its performance in case of any external change? Ex) There is a monitoring mechanism in place to alert the team if there is a significant change in the distribution in the input data beyond a pre-defined threshold 
 - [ ] **G.4 Bias reinforcement**: Can the feedback loop be reinforcing any existing biases? Ex) if loans predicted to default are denied. Is there any user interaction with the output? Ex) user clicking on links recommended by the algorithm
 
*Contact: sal87@cam.ac.uk*
