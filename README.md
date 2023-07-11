# Data competency assessment

## Dependencies

You should have received the following notes by email prior to the assessment:

1. You will need an a GitHub account with multi-factor authentication enabled.
2. You will need your reviewers GitHub username or email address.
3. You will need git installed on your machine. If you are a Windows user, you can download it from [here](https://git-scm.com/downloads).
4. We suggest using Visual Studio Code to complete the assessment. You can download it from [here](https://code.visualstudio.com/download). If you have a preferred text editor or IDE, you are welcome to use that instead, but VS Code has excellent support for markdown editing (See [Markdown preview](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview)).
5. You can assume that your reviewer has `python 3` and `pip3` installed on their machine. If you wish to use a different language, please provide a comprehensive environment setup guide. The reviewer will make a best-effort attempt at following your instructions, but you will be penalised if your instructions have missing steps or are unclear. For your decision making, at least one portion of the assessment will require the writing of unit tests.

> **Note**: If you were not previously instructed on the above, please let your reviewer know immediately and you may have an additional **45 minutes** to complete the assessment.

## Instructions 

This competency assessment consists of a theory section and a practical component.

1. Answers should be committed in this `README.md` underneath the relevant sections.
2. Do your work on the `main` branch.
2. You must provide instructions for running your code, ideally copy-pastable commands. The instructions should work on Windows unless you do not have a Windows machine, in which case please state this at submission. If your code requires any dependencies or installations, please list them in the instructions. You can assume `python 3` and `pip3` is installed on the reviewers machine.
3. You can find the data files (`lab_data.txt` and `medicine_data.csv`) for the practical section in the `data` folder.
4. Please place scripts in the `code` folder and unit tests in the `tests` folder.
5. Should you need to add any images or screenshots, please place them in the assets folder and embed them in the markdown document (See: [Markdown: Basic Syntax](https://www.markdownguide.org/basic-syntax/#images-1)).
6. Your answers to `Section A: Theory` should be one commit, and your answers to `Section B: Practical` should each be a separate commit. Please give your commits appropriate messages.
7. Where necessary, please use code fencing to denote code blocks in markdown. See: [Markdown: Fenced Code Blocks](https://www.markdownguide.org/extended-syntax/#fenced-code-blocks), with correct highlighting, if applicable.
8. You may use the internet to assist you with your answers. 

> **Note**: Once you have completed the assessment, please email a link to your forked repository to your reviewer -- by **12.30pm** if your assessment time was 9am-12pm, or by **3.30pm** if your assessment time was 12pm-3pm.

## Submission
   
Please fork this repository to your own GitHub account. You will need to give your reviewer access to your forked repository. You can do this by going to `Settings > Manage Access` and adding your reviewer as a collaborator.
## Overview

- The theory section should take approximately 30 minutes to complete. 
- The practical section should take approximately 90 minutes to complete, however you have 
extra time. 

## Assessment (Section A: Theory)

1. The Provincial Health Data Centre contains data from multiple different sources and acquires data in different formats. List at least 3 factors that would be crucial for harmonising data into a consolidated environment.  

**[3 marks]**

---
**Answer Q1**  
Please answer here.

---
 
2. At the Provincial Health Data Centre we often receive requests for data for analysis purposes, whereby it is unnecessary for the analyst to know the identity of the patient. As part of your work you may have to release a fully de-identified dataset (i.e., a dataset from which you could not re-identify the patients included). List at least two points describing how you could obfuscate the data so that it could not be re-identified.  

**[2 marks]**

---
**Answer Q2**  
Please answer here.

---

3. An HbA1c level of 6.5% or more is considered high enough to diagnose diabetes, while values lower than 6.5% indicate healthy patients. A programmer incorrectly wrote the code to identify diabetics as: HbA1c > 6.5% and as such 300 patients with HbA1c = 6.5% were classified as healthy patients. In statistical terms, what could those 300 patients could be classified as? 

A. False positives  
B. False negatives  
C. Type 1 error

**[2 marks]**

---
**Answer Q3**  
Please answer here.

---

4. Knowing the medication a patient is taking often can indicate what health condition they have. For example if a patient is regularly prescribed insulin it is likely that they have chronic diabetes. However, in some cases patients that do not have chronic diabetes may be given insulin for short periods in hospital. Suppose there was a register of all patients who have been diagnosed with chronic diabetes by a doctor. You have been tasked with trying to reproduce this register based on insulin dispensing data alone. What statistical term would best describe the percentage of patients with chronic diabetes who were correctly identified as having the condition?

A. Specificity  
B. Sensitivity  
C. True negative rate  

**[2 marks]**

---
**Answer Q4**  
Please answer here.

---

5. There are two laboratory tests that can be used to monitor HIV over time, viral load and CD4 count. An HIV+ patient on treatment will typically have one viral load and CD4 count test per year. When preparing data for an analyst they might request the dataset in "long" or "wide" format. 
Which of the following dataset descriptions best describes a "wide" dataset?

A. Each line in the dataset contains one test result, with only a few columns  
B. Each line in the dataset contains one patient, with multiple columns  

**[1 mark]**

---
**Answer Q5**  
Please answer here.

---

## Assessment (Section B: Practical)

For this practical assessment you have been given the following two files:

- **laboratory_data.txt**: This contains HbA1c test results for diabetic patients including: patient 
ID, sex, date of birth, lab test type, lab test date, and lab test result.
- **medicine_data.csv**: This contains medicine dispensing data for diabetic patients including: 
patient ID, sex, date of birth, medicine name, and dispensing date.

> **Note:** Please note that the patient ID is a unique identifier for the patient; i.e., each unique person has one "patient ID" that can be used to identify them.

### **Question 1: Data Imports [30 marks, approx. 70 minutes]**

1. Using a language of your choice, write a script to import the data and add it to the `code` folder.

**[5 marks]**

2. Add unit tests to the repository (`tests` folder), with instructions for use, and test the data import script, asserting:
   - The number of columns in each file.
   - The number of rows in each file.
   - The number of unique patient IDs in each file.

**[15 marks]**

3. Add a GitHub Action to the repository that runs the unit tests on each commit to the `main` branch. 

**[10 marks]**

---
**Answer 1**  
Please add any notes, instructions or other information here.

---

### **Question 2: Data Transformation [15 marks, approx. 40 minutes]**

You have been provided data in a long format. In this question you will be required to construct a wide dataset that could be used to track each individual patient’s health. Your dataset should contain one line per patient and should contain the columns listed below.  

Write a script to transform the data into a wide format, output it to a file and add it to the `code` folder. 

Your dataset must have the following columns:

#### Dataset columns

1. **Patient ID**
2. **Sex** -- Standardised as either "M" or "F"
3. **Age category** -- Calculate the age in years as of today’s date and categorise into the following age brackets: 
   - `<30`
   - `30-39`
   - `40-49`
   - `50-59`
   - `>=60`
4. **Medicine category** -- Categorise the medications the patient is taking into the following drug categories:
   - Insulin only
   - Metformin only
   - Insulin AND metformin
   - No drugs dispensed
5. **Last medicine dispensing date** -- i.e. the date corresponding with the most recent dispensing 
of medicines
6. **Number of times medicines were dispensed** -- i.e. count of times medicines have been dispensed
7. **HbA1c test date**
8. **HbA1c test result**
9. **Diabetic treatment follow up flag** -- This should be a binary field (1/0), where a value of 1 indicates that the patient has a uncontrolled HbA1c (HbA1c >=8) OR they are not taking medication.

---
**Answer 2**  
Please add any notes, instructions or other information here.

---