# The solution of the second day of competition 

## Model - Legal Bert
### F1 micro score - 0.905470635559131
### Rank - 12 / 31

# About the problem 
The problem will ask you to create a classification of legal documents representing laws in force in the European Union (EU) with respect to the directory they belong to.

The "Directory of legal acts", i.e. the hierarchy of rules in force in the EU, includes 20 main chapters, divided into various sub-chapters:

01 General, financial and institutional matters

01.07 Statistics
01.10 Principles, objectives and tasks of the Treaties
01.20 General provisions
01.30 Scope of the treats
…

02 Customs Union and free movement of goods

02.05 General
02.07 Statistics
02.10 General customs rules
…

03 Agriculture

…

 

The sub-chapters at depth 2 have been coded with strings separated by a hyphen (for example '01-07', '02-10') which represent the target of the classification, the purpose of which is to process the text of the law and/or the regulatory references and predict the sub-chapter it belongs to.

 

# About the dataset 
The training data is enclosed in a table with 9941 rows and 4 columns. Each line relates to a single law, and for each law it shows the following attributes:

CELEX_ID, i.e. the unique alphanumeric identifier of the law;
text, i.e. the text of the law in plain text format;
Directory code, i.e. the string separated by a dash that represents the chapter and sub-chapter of the EU in which the law is inserted;
Citations, i.e. the normative references present in the law, reported in turn in plain text format.

The test data is provided unlabelled in a table of 2486 rows and 3 columns (the target variable “Directory code” is missing).

The Dataset does not contain duplicate laws and is unbalanced, i.e. there is a significant difference between the number of laws present in each sub-chapter. There are also cases in which the chapter does not have sub-chapters, and in these cases only the code relating to the main chapter is reported as a label (for example 18). CELEX_IDs are unique.

 

Labels: the labels represent the main chapter and sub-chapter in which each law is included, with a hyphen as a separator.

 

Objective: we want you to implement a classifier which, after any appropriate preprocessing of the text in natural language and using Machine Learning methods, predicts the subchapter to which each law belongs, i.e. its Directory code. Each law is associated with a single Directory code, corresponding to the second level of hierarchy in the EU classification.
 
