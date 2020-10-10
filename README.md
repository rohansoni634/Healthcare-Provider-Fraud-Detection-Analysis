# Healthcare-Provider-Fraud-Detection-Analysis 

### Blog link : medium.com/@rohansoni.jssaten2019


The main goal of this project is to ’Predict the potentially fraudulent providers’ based on the claims filed by them. Also we will discover what are the most important variables helpful in detecting the behaviour of potentially fraud providers so that we may flag such claims and perform in depth investigation on them.


<b><u>Problem Description</b> : Health insurance is like a backbone to the citizens of a country that deals with
many hardships along with uncertainty in their health condition. To contract the burden of paying huge
medical bills governments as well as private insurance companies provide health insurance schemes on
some premiums to be paid in installments.
One of the most important problems in the insurance industry is fraud in claims which causes substantial
losses to the insurance providers..The cost of determining or predicting potential fraud in any claim
submitted is very high because if it is done incorrectly it may irritate legitimate customers and it may result in
delayed claims adjudication.Healthcare fraud is an organized crime which involves peers of providers,
physicians, beneficiaries acting together to make fraud claims.Provider Fraud is one of the biggest problems
facing Medicare. For example an uninsured person may unlawfully get insurance benefits disguising himself
as an insured person, or some provider may wrongly put an exaggerated amount on a member's bill later to
be settled with the insurance provider.


<b><u>Problem Statement</b> :
<ul>
<li>Predict the probability that a provider is potential fraud and flag them accordingly.</li>
<li>Discover important variables that might be helpful in flagging providers as potential fraud.</li>
</ul>


<b><u>Business constraints</b>:
<ul>
<li>Cost of misclassification is very high.</li>
<li>No strict latency requirements.</li>
<li>Model interpretability is very important.</li>
</ul>

<b>Data </b>:
<a href="https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis">Data-Download</a>
We have 4 csv files for training/testing purposes.These data files are procured from kaggle. These files
contain viable information of the insurance scheme <b>beneficiaries</b>,patients who got admitted in the hospital
and undergone some medical procedure and diagnosis<b>(inpatient data)</b>,patients who visited hospital for
some procedure or diagnosis or both but were not admitted<b>(outpatient)</b> and <b>medical service provider ID's
labelled as potential fraud or not</b>.
  
### Some important columns in the dataset that we have :
#### 1. Inpatient and outpatient data: 
<ul>
<li><b>ClaimID</b> : This a unique id for each claim submitted</li>
<li><b>Bene_ID</b> : contains Unique Id of the beneficiaries registered for insurance scheme</li>
<li><b>AttendingPhysician</b> : column contains the id of the physicians who attended the patient.</li>
<li><b>OperatingPhysician</b> : column contains the id of the the physicians who operated on the
patient</li>
<li><b>ClmDiagnosisCode</b> : contains Diagnosis Codes for that are performed on the patients by
providers.</li>
<li><b>ClmProcedureCode</b> : contains procedures codes that patients undergo.</li>
<li><b>Provider</b> :  unique Id of the healthcare providers.</li>
<li><b>InscClaimAmtReimbursed</b> : Total amount paid to the claimant after settlement.
</li>
<li><b>ClaimStartDt / ClaimEndDt </b> : These columns has the date on which the claims were
submitted and the date when claims got settled respectively.
</li>
<li><b>AdmissionDt / DischargeDt </b> :: Date on which the patient got admitted in hospital and the
date on which patient got discharged .Applicable for only inpatient data.</li>
</ul>

#### 2. Beneficiaries data :
<ul>
<li><b>Bene_ID</b> : contains Unique Id of the beneficiaries registered for the insurance scheme.</li>
<li><b>DOB</b> :  Date of birth of the beneficiaries registered for the insurance scheme.</li>
<li><b>Gender</b> : Gender of the beneficiaries registered for the insurance scheme.
</li>
<li><b>State/Country</b> : contains state/country code for the registered members.</li>
<li><b>Premedical conditions</b> :  There are some columns such as RenalDiseaseIndicator,ChronicCond_Depression,ChronicCond_Diabetes etc to indicate if
the member has any prior medical condition.
</li>
</ul>

#### 3. Target data:
<ul>
<li><b>Provider</b> : This a unique id for each of the healthcare providers.</li>
<li><b>Target</b> :  This column has two values Yes and No indicating if the corresponding provider is
flagged as potential fraud or not.</li>
</ul>
  
<b><u>Machine Learning Problem</b>: 

This is a binary classification problem,for a given set of features we
need to predict whether the corresponding provider needs to be flagged as potential fraud or not.

<b>Metric</b>: 
Since most of the providers are not a potential fraud,this makes our dataset Imbalanced .Also we
need to be very sure while flagging a provider as potential fraud.To evaluate model performance in this
scenario we can use following metrics:
<ul>
<li><b>1. log-loss</b></li>
<li><b>2. Binary Confusion Matrix</b></li>
<li><b>3. Precision,recall and F1 score</b></li>
<ul>
