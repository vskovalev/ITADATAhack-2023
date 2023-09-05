# The solution for the first day of ITADATAhack competition

## Model - Legal Bert

### F1 Micro Score - 0.939886271324127
### Place - 12


# About the problem 

The problem will ask you to create a classification of legal documents representing laws in force in the European Union (EU) with respect to the directory they belong to.

The "Directory of legal acts", i.e. the hierarchy of rules in force in the EU, includes 20 main chapters:

General, financial and institutional matters;
Customs Union and free movement of goods;
Agriculture;
Fisheries:
[…]

Each chapter is divided into sub-chapters at various levels. 
The chapters have been coded with integers from 1 to 20 and represent the target of the classification, 
which must process the text of the law and/or the normative references and predict the chapter to which it belongs.


# About the dataset 
The training data is enclosed in a table with 51968 rows and 4 columns. Each line relates to a single law, and for each law it shows the following attributes:

CELEX_ID, i.e. the unique alphanumeric identifier of the law;
Text, i.e. the text of the law in plain text format;
Directory code, i.e. the whole number between 1 and 20 which represents the main chapter of the EU in which the law is inserted;
Citations, i.e. the normative references present in the law, reported in turn in plain text format.
 

Test data is provided unlabelled in a table of 12292 rows and 3 columns (the target variable “Directory code” is missing).

The Dataset has been rebalanced by oversampling the laws belonging to underrepresented chapters, which is why there are duplicate CELEX_IDs.

Labels: the labels represent the main chapter in which each law is included, at this stage they are integers between 1 and 20.

Objective: we want you to implement a classifier which, after any appropriate preprocessing of the text of the law and/or the references in natural language and using Machine Learning methods, predicts the chapter to which each law belongs, i.e. its Directory code. Each law is associated with a single Directory code, corresponding to the first level of hierarchy in the EU classification.
 
