# Penalty Estimation: Data & Annotation details 
 
Dataset:  Legal case files (adjudication orders ONLY) scraped from the SEBI website in both pdf and text format 
 
Dataset Path: 
Data_/casefile_analysis/penalty_violation/Non Annotated/Data - PDF /
Data_/casefile_analysis/penalty_violation/Non Annotated/Data - TXT/

Scraped Data Path: 
Data_/casefile_analysis/penalty_violation/Non Annotated/Data - Scraped - PDF/
 
Annotations: Parsed (converted to text from pdf) legal case files from the datasets annotated with semantically relevant labels mentioned below. 
 
Labels:
* Facts (Material) – Statements that contain information about the case that is relevant and important in deciding the outcome as well as the violation and penalty, if any.
* Facts (Procedural) – Statements that contain generic information on the procedure duly followed by the authorities to set the process of adjudication in motion.
* Statutory Facts – Statements that invoke rules, regulations, acts and orders by the SEBI, either by using their representative names and numbers or by quoting them in totality.
* Related Facts – Statements made in a general sense, including truisms, re emphasis of statutory facts which do not constitute the facts of the instant case, but are material in deciding its outcome.
* Issues Framed – Statements that are in the form of questions, that are the principal questions of law or fact that need to be adjudicated upon.
* Subjective Observation – Statements that are based on the personal feeling or conclusion of the adjudicating officer or tribunal member, based on their reading of the facts and defendant claims.
* Defendant Claims – Statements that elaborate the stand taken by a defendant/accused by way of countering or accepting, or partially countering or partially accepting the accusations/allegations made on him.
* Allegation – Statements that accuse individuals or entities of violating a regulation or a set of regulations, based on the understanding of facts by SEBI.
* Penalty – Statements that talk about the monetary penalty that should or should not be imposed, including the reason given therein by way of the regulation violated.
* Violation – Statements that conclusively talk about the violation of a particular regulation or a set of regulations, acts and rules.
 
 
Annotations Path:
Data_/casefile_analysis/penalty_violation/Annotated/Annotated - CSV/
 
Annotations are stored filewise. The CSV file contains 3 columns, namely sentence_id, label and sentence. The sentence id is assigned with F<filename>_S<sentence number> 
 
Number of adjudication orders annotated by legal experts = 29 
Number of adjudication orders validated by legal experts = 9 
Number of PIT orders scraped from SEBI = 1463 

 
Non Validated Data Path: Data_/casefile_analysis/penalty_violation/Validation Data/Non Validated Files/
Validated Data Path: Data_/casefile_analysis/penalty_violation/Validation Data/Validated Files/
 
To automate the annotation process, an automatic annotation pipeline has been set up which parses, segments and labels the sentences using a prelim model that was trained using the original annotation dataset. These labels are then validated by a legal expert. As this process is automated, it is prone to segmentation errors thus the validated data has not been merged with the original dataset. 
In the validated files, the label that starts with a capital letter has been modified by the legal expert i.e it was incorrectly assigned a label by the model, and all the labels starting with small case letters, were correctly labelled by the model. This also helps evaluate the performance of the model on unseen data.
 
 
 
