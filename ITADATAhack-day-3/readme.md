# The solution for the first day of ITADATAhack competition

## Model - Legal Bert

### Jaccard Index - 0.810136765888978
### Place - 16 / 31


# About the problem 

The problem will ask you to create a classification of legal documents representing laws in force in the European Union (EU) with respect to the subdirectories to which they belong.

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

 

The sub-chapters at depth 2 have been coded with strings separated by a hyphen (for example '01-07', '02-10') which represent the target of the classification, whose purpose is to process the law text and predict the sub-chapters of membership. In this case, we are dealing with a multilabel classification problem, given that each law can be included in several sub-chapters and the belonging of a law to a sub-chapter is not exclusive.

 

# About the dataset

The training data is enclosed in a table with 9941 rows and 96 columns. Each line relates to a single law, and for each law it shows the following attributes:

text, i.e. the text of the law in plain text format
Citations, i.e. the normative references present in the law, reported in turn in plain text format
93 indicator-type columns, one for each distinct value of Directory code (represented at depth 2), which are the labels of the laws
 
The name of each column is the hyphen-separated string representing the chapter and sub-chapter of the EU in which the law is inserted and its values ​​are binary. A law can have multiple columns with values ​​equal to 1, this means that that law is classified in several distinct chapters-subchapters.

Test data is provided unlabeled in a table of 2486 rows and 3 columns (the 93 “Directory code” target variables are missing).

The Dataset does not contain duplicate laws and is unbalanced, i.e. there is a significant difference between the number of laws present in each sub-chapter. There are also cases in which the chapter does not have sub-chapters, and in these cases only the code relating to the main chapter is reported as column name (for example 18). CELEX_IDs are unique.

Labels: the labels represent the main chapter and sub-chapter in which each law is included, with a hyphen as a separator. There are 93 distinct labels that can be applied to each law in a non-exclusive way.

Objective: we want you to implement a classifier which, after an appropriate preprocessing of the text in natural language and using Machine Learning methods, predicts the sub-chapters of each law, i.e. its Directory code. Each law can be associated with different Directory codes, corresponding to the second level of hierarchy in the EU classification.

