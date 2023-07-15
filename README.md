# FS-DAG (Few-Shot : Domain Adapting Graphs)

Information Extraction from documents is finding its application across various industry as a push for Digitization and Automation of processes. Various Tasks for Document Understanding are an active field of research in industry and academia. Our paper **FS-DAG** : Few Shot Domain Adapting Graph Networks for Visually Rich Document Understanding proposes multiple novel techniques to solve the problems more effectively and effficiently.

To usher further research in the domain we open-source 2 categories of datasets with industry specific document types for benchmarking different models for similar tasks under few-shot learning environment.

## Installation

```
$ git clone https://github.com/oracle-samples/fs-dag.git
$ cd fs-dag
$ tree -d
```

## Documentation

For the Visually Rich Document Understanding (VRDU) task of Key Information Extraction(KIE) , many publicly available datasets are available, like SROIE ,CORD , and WildReceipt , which are typical document receipts. Other datasets like FUNSD  contain various types of forms with only high-level key-value pairs, which are well-suited for academic research but do not capture the industry requirements of data extraction with fine-grained classes.
The publicly available datasets are concentrated on receipts, invoices, and simple forms without adding much diversity to the industry domain/use cases. The publicly available datasets minimally capture those forms filled character-by-character within boxes/placeholders and have wide-scale relevance in the financial, medical, and logistics industries. Thus to further fuel the research for VRDU task, we open-source two categories of datasets as follows :


# Table of Content
1. [Description](#desc)
    a. [Category 1](#cat1)
        - [Folder Structure](#fold1)
        - [File Description](#filedesc1)
    b. [Category 2](#cat2)
        - [Folder Structure](#fold2)
        - [File Description](#filedesc2)
2. [Tasks](#task)

---
<a name="desc"></a>
## Dataset Categories
---
<a name="cat1"></a>
### Category 1

It contains 5 documents types as described :

1. **Ecommerce Invoice** : Real invoices downloaded for items bought at a particular e-commerce site.
2. **Adverse Health Reaction Form** : Contains filled forms of VAERS. The forms are filled by human annotators using non-existential/faker data that cannot be used to identify any human thus removing PII.
3. **Medical Invoice**  : Contains synthetically generated Medical Invoices for various treatment.
4. **University Admission Form** : Contains filled application forms for University of Michigan. The forms are filled by human annotators using non-existential/faker data that cannot be used to identify any human thus removing PII.
5. **Visa Form** : Contains Non-Immigrant Visa Application form issued by U.S. Department of State. The forms are filled by human annotators using non-existential/faker data that cannot be used to identify any human thus removing PII.

<a name="fold1"></a>
#### Folder Structure
```
.
|-- cat_1
|   |-- adverse_health_reaction_form
|   |-- ecommerce_invoice
|   |-- medical_invoice
|   |-- university_admission_form
|   `-- visa_form

```

Evert dataset folder has the following structure :

```
.<dataset>
|-- class_list.txt
|-- images
|-- train_05.txt
|-- test.txt
`-- ocr_test.txt
```

<a name="filedesc1"></a>

#### Files Description

1. ```class_list.txt``` : Contains the list of fine-grained key-values (classes) that needs to be extracted from the document

2. ```images``` : Folder contains all the document images released as apart of the dataset.

3. ```train_05.txt``` : Contains the train split used for training various models with GT annotations for the files.
4. ```test.txt``` : Contains the test split used for testing various models with GT annotations for the files.
5. ```ocr_test.txt``` :  Contains the test split used for testing the robustness of  various models with OCR errors introduced using a probability of 0.1 in the GT annotations.

---
<a name="cat2"></a>
### Category 2

It contains 7 documents types which are forms with fields filled character-by-character. These type of forms are used across various industry verticals and have be **programmatically filled**. The document types are described as follows :

1. **Medical Authorization** : Contains an authorization form for medicine prescriber's use only.
2. **Personal Bank Account** : Contains forms that needs to be filled to open a new personal bank account by physically visiting the bank office.
3. **Equity Mortgage**  : Contains forms used to pledge equity stocks as collateral/mortgage.
4. **Corporate Bank Account** : Contains forms that needs to be filled to open a new corporate bank account by physically visiting the bank office.
5. **Online Banking Application** : Contains forms that needs to be filled to open a new corporate bank account by using online banking applications.
6. **Medical Tax Returns** : Contains form by the Department of Revenue Administration for filing Medicaid Tax Returens
7. **Medical Insurance Enrollement** : Contains Group Enrollment Form for Medical Insurance.

<a name="fold2"></a>
#### Folder Structure
```
.
|-- cat_2
|-- corporate_bank_account
|-- equity_mortgage
|-- medical_authorization
|-- medical_insurance_enrollment
|-- medical_tax_returns
|-- online_banking_application
`-- personal_bank_account


```
Evert dataset folder has the following structure :

```
.<dataset>
|-- class_list.txt
|-- images
|-- train_05.txt
|-- test.txt
|-- ocr_test.txt
|-- annotations
|-- statistics_entity.xlsx
|-- statistics_word.xlsx
`-- visualise
```
<a name="filedesc2"></a>
#### Files Description

1. ```class_list.txt``` : Contains the list of fine-grained key-values (classes) that needs to be extracted from the document

2. ```images``` : Folder contains all the document images released as apart of the dataset.

3. ```train_05.txt``` : Contains the train split used for training various models with GT annotations for the files.

4. ```test.txt``` : Contains the test split used for testing various models with GT annotations for the files.

5. ```ocr_test.txt``` :  Contains the test split used for testing the robustness of  various models with OCR errors introduced using a probability of 0.1 in the GT annotations.

5. ```annotations``` : The folder contains annotations of all the 50 images at word level and entity level, which can help in creating new task or solve more problems. Files ending with ```_word.json``` contain word level annotations while files ending with ```_entity.json``` contain entity level annotations
5. ```statistics_entity.xlsx``` : Contains the distribution of key-value fields/class of the dataset at entity level.
5. ```statistics_word.xlsx``` : Contains the distribution of key-value fields/class of the dataset at word level.
5. ```visualise.txt``` : The folder visualise the bounding box for each word in files ending with ```_word.png``` in blue color. Images ending with ```_entity.png``` contain word level bounding box in **red** while entity level bounding box in **blue**.

<a name="task"></a>
## Tasks

The dataset can be used for various Document Understanding tasks and models like :

1. **Key Information Extraction (KIE)** : Extracting key-value pairs from documents
2. **Entity Linking (EL)** : The entity level annotation in Category 2 dataset can be exploited to benchmark entity linking models.
3. **Optical Character Recognition(OCR)** : OCR models can be used to check efficiency in complex real world documents across both categories of dataset.

## Examples

*Describe any included examples or provide a link to a demo/tutorial*

## Help

Reach out to :
1. Amit Agarwal (Senior Applied Scientist, OCI)
2. Srikant Panda (Senior Applied Scientist, OCI)
3. Kulbhushan Panda (Senior Director, OCI)

## Contributing

*If your project has specific contribution requirements, update the CONTRIBUTING.md file to ensure those requirements are clearly explained*

This project welcomes contributions from the community. Before submitting a pull request, please [review our contribution guide](./CONTRIBUTING.md)

## Security

Please consult the [security guide](./SECURITY.md) for our responsible security vulnerability disclosure process

## License

*The correct copyright notice format for both documentation and software is*
    "Copyright (c) [year,] year Oracle and/or its affiliates."
*You must include the year the content was first released (on any platform) and the most recent year in which it was revised*

Copyright (c) 2023 Oracle and/or its affiliates.

*Replace this statement if your project is not licensed under the UPL*

Released under the CC0 1.0 Universal as shown at [license guide](./LICENSE.txt).
