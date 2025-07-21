This document details the processing of the survey data on the experiences and perceptions of youths around online body shaming, collected in the framework of the Elephant Talk project.

The goal of the document is to foster transparency around the processing of the data, both to promote replicability and to spur reflections about areas for improvement in the data collection for future work. It can also be used as a basis for documentation in the case it is decided to create a GitHub repository (or similar) to open source the data, or to populate the methodology section of the website.

The process of combining the 8 survey response files, one for each language, in a single cleaned English file has been achieved with a mix of Python, manual data cleaning, and assistance from Claude.ai, as detailed in the following paragraphs.

# 1. Creation of a dictionary for translating language variations
The main challenge in preparing the data from the analysis came from the absence of a machine-readable master file containing the English equivalent for all of the questions and possible answers to the questions in the different languages. This master file has been prepared by combining three different strategies.

## a. Create a dictionary for the questions
*Resulting file: question_dictionary.csv*<br>
Claude.ai was used to read through the 8 language versions of the survey, received as 8 different .docx files with the questions and answers in the same order, and create a .csv file with one row for each question and one column for each language.
The file was then enriched manually, assigning a question id (Q_ID), a short name (short_id), a question type (QTYPE), and an English translation (en) to each question. The English translations have been derived from the Elephant Survey EN questionnaire available on Form Bricks.
Because of discrepancies in the wording of the questions in the original .docx files and in the actual surveys, the file has been manually cleaned to match the wording and spelling of the questions actually used in the 8 final surveys.

## b. Create a dictionary for the fixed answers (single-select, multi-select, rating, and ranking questions)
Claude.ai was used to read through the 8 language versions of the survey, sent by Maghweb as 8 different .docx files with the questions and answers in the same order, to create a .csv file with one row for each question+answer combination and one column for each language.
The file was then enriched manually, assigning an answer id (A_ID) and an English translation (en) to each question. The English translations have been derived from the Elephant Survey EN questionnaire available on Form Bricks.
Because of discrepancies in the wording of the answers in the original .docx files and in the actual surveys, the file has been manually cleaned to match the wording and spelling of the answers actually used in the 8 final surveys*.

*In question 6, the Portuguese survey had an extra option in comparison to the other language surveys, as it had two different options(“Comparações de aparência física com outros” , “Comparações sobre aparência física com outras pessoas”) for the same possible answer “Comparisons of physical appearances to others”.

## c. Create a dictionary for the answers to free text answers
Manual cleaning, with the assistance of Google spreadsheets, Claude.ai, and Open Refine, was used to create a dictionary for the translation of free text answers.These answers include both answers tofree text questions and answer to the “Other, specify” option in single select/multi select questions.

### STARTING FILE
The Python script used to create a single .CSV file outputed a list of answers associated with each question and language that were not present in the previous dictionary of predetermined fixed answers. 

### GOOGLE SHEETS CLEANING
The starting file has been enriched with an en column containing the English translation. Such translations have been achieved through the GOOGLETRANSLATE function of Google Sheets and then cleaned as described below.
The English translated answers to “Other, specify” options or to the “location” question have been cleaned with traditional Google Sheets formulas and checked manually, as there were only a few variations*. 

*In multiple locations were provided by the same respondent, only the first one was considered. There has been no attempt to edit locations to harmonize based on location type to respect perceived and declared location/identity of the respondents (some provided cities, others regions or neighbourhoods, etc.).
For free text answers to questions 9 - 10 - 18 -27, on the other hand, there was much more variation, and thus the English translations have only been cleaned automatically with functions to uniform the lowercase, remove extra spaces,etc.

### OPEN REFINE CLEANING
The resulting file with all the free-text answers has then been uploaded to OpenRefine, to spot and resolve inconsistencies.
Answers which will be excluded from the data analysis, for example because they include meaningless letters, have been converted to empty, along with answers like “I don’t know” (because people who have not answered the question might also “not know”, and thus, in the analysis, they will all fall in the category “Don’t know/Didn’t answer”).

## d. Create a unified dictionary for the answers
*Resulting file: answer_dictionary.csv*<br>
The fixed answers and the cleaned free text answers have been joined in a single file, optimized for proceeding with the automatized translation of the response file.

# 2. Creation of a single translated CSV file
A Python script has been used to open the 8 language files and combine them in a single csv file, with questions’ short_id as column names. This script was the first time also used to generate the starting translation file for the free-text answers.

Once the two translation files were in place (question_dictionary.csv; answer_dictionary.csv), the script was run again to translate the combined file. 
For this translation task, the script iterated through the different columns (each with answers to a question in the original language) and created a new derived column with the same name and the “_EN” suffix, containing the translated answers takend from the three dictionary files.
