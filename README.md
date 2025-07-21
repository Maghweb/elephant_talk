# The Elephant Talk project
Elephant Talk is a youth active citizenship project created by Maghweb in collaboration with Impact Hub Labs, Polylogos and Young Educators funded by the EACEA in the CERV programme, Citizen’s Engagement and Participation strand. The project aims to engage young citizens across Europe in a collective, international collaborative **data gathering and visualisation action against online gender-based hate speech with youth workers from their different communities.** 

# 👉 See full survey results: [stophatespeech.eu](https://www.stophatespeech.eu)

## Index:

- [What data you will find in this repo](#repo-contents)
- [Overview of the survey structure](#survey-structure)
- [Methodological note when interpreting results](#methodological-note)
- [Project Funding](#project-funding)

## Repo contents

**This repo contains the data collected through the Elephant Talk survey that ran until April 30th, 2025**. The survey has been administered through the open-source and GDPR-compliant platform [FormBricks](https://formbricks.com/). The survey was sent in 8 different language versions: Catalan, Croatian, Greek, Italian, Portuguese, Romanian, Slovenian, and Spanish. A total of 1.395 respondents began the survey, of which 706 (51%) completed all questions. The process of combining the 8 survey response files, one for each language, in a single cleaned English file has been achieved with a mix of Python, manual data cleaning, and assistance from Claude.ai, as detailed in the "Data Cleaning Documentation" file.

### DATA FILES
#### 1. The raw data files
One file for each language result, as outputted by FormBricks on April 30th, 2025. Includes also unfinished surveys which have been excluded from the analysis.
The language codes are the following, used throughout all files

| code | language |
|---------------|--------------|
| cat | Catalan            |
| esp | Spanish            |
| gr | Greek            |
| hr | Croatian            |
| it | Italian            |
| pt | Portuguese            |
| ro | Romanian            |
| slo | Slovenian            |

#### 2. Combined and translated result file - WIDE FORMAT
In this file, all language responses from the 8 files are combined, and each question contains both the original response and the translated response (with the suffix "_EN" in the column name. Multiple choice answers are separated by a pipe character ("|"). The file includes also unfinished surveys which have been excluded from the analysis.<br>
<img width="894" height="321" alt="wide" src="https://github.com/user-attachments/assets/58099ce4-ef47-44c4-b51c-36f798042bf3" /><br>

#### 3. Combined and translated result file - LONG FORMAT
In this file, there is one row for each response (english translation) given by each participant to each question. The file includes also unfinished surveys which have been excluded from the analysis.<br>
<img width="349" height="247" alt="long" src="https://github.com/user-attachments/assets/90d19a8d-2642-4d6e-a29a-2c0c18b418e3" /><br>

#### 4. Frequency file
This file contains the number of responses (absolute and %) for each answer, with combined breakdowns by language, age and gender (only M / F / Non-binary), along with the overall totals. The file  includes only the questions used in the analysis narrated in [the project's website](https://www.stophatespeech.eu). This file is meant as a file to facilitate analysis and visualizations for those who don't have the time or expertise to process the original survey files. **Note that, just like in the analysis, the frequencies are calculated only among finished surveys.**<br>
<img width="750" height="416" alt="Screenshot 2025-07-21 at 14 18 31" src="https://github.com/user-attachments/assets/53746d7f-6088-48a1-b982-54c0df179995" /><br>

### META
#### 1. Documentation of data processing
This document details the processing of the survey data. The goal of the document is to foster transparency around the processing of the data, both to promote replicability and to spur reflections about areas for improvement in the data collection for future work. 

#### 2. Question dictionary 
A .csv file with the English translation and the original text of all the questions contained in the survey. The file has been used to translate the language surveys into the translated combined file.<br>
<img width="1280" height="291" alt="q_dict" src="https://github.com/user-attachments/assets/9f6dca77-57aa-4262-835e-a8378dbd4485" /><br>

#### 3. Answer dictionary 
A .csv file with the English translation and the original text of all the answers contained in the survey, including free text answers. The file has been used to translate the language surveys into the translated combined file.<br>
<img width="865" height="299" alt="a_dict" src="https://github.com/user-attachments/assets/a2439e79-f158-4853-b77d-f473db25ed5d" /><br>

## Survey structure
The survey consists of 27 questions, of the following types:

### Question types

| Question type  | N. questions |
|---------------|--------------|
| single select *| 9            |
| multi select *| 9            |
| free text     | 5            |
| rating        | 3            |
| ranking       | 1            |


*1 of the 9 single select questions also included a “Other, specify” option, which could be populated with free text*<br>
*8 of the 9 multi select questions also included a “Other, specify” option, which could be populated with free text*

### Questions

| Q_ID | short_id           | Question                                                                                                                                                                                  | QTYPE          |
|------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------|
| 1    | age                | How old are you?                                                                                                                                                                          | single select  |
| 2    | gender             | What's your gender identity?                                                                                                                                                              | single select *|
| 3    | location           | Where do you live?                                                                                                                                                                        | free text      |
| 4    | occupation         | What are you currently involved with?                                                                                                                                                     | multi select *|
| 5    | platforms          | Which of the following platforms do you use the most?                                                                                                                                     | multi select *|
| 6    | actions_done       | Have you ever done any of the following online?                                                                                                                                           | multi select *|
| 7    | agree_sentences    | Select the sentences you agree with                                                                                                                                                       | multi select   |
| 8    | heard_term         | Have you ever heard the term "online body shaming"?                                                                                                                                        | single select  |
| 9    | interpretation     | How would you describe it in your words?                                                                                                                                                   | free text      |
| 10   | reasons            | What do you think are the main reasons for online body shaming?                                                                                                                           | free text      |
| 11   | common             | In your opinion, how common is body shaming on your social media?                                                                                                                         | single select  |
| 12   | target_groups      | Which groups do you think are most frequently targeted by online body shaming?                                                                                                             | ranking       |
| 13   | witnessed          | Have you ever witnessed body shaming incidents online?                                                                                                                                     | single select  |
| 14   | experienced        | Have you ever experienced body shaming online?                                                                                                                                             | single select  |
| 15   | encountered_social | What platform have you encountered body shaming on?                                                                                                                                        | multi select *|
| 16   | encountered_forms  | What form of body shaming have you encountered?                                                                                                                                            | multi select *|
| 17   | encountered_reaction| If you have ever witnessed or experienced online body shaming, how did you react?                                                                                                          | multi select *|
| 18   | associated_words   | What kind of words have you encountered that you would consider to be body shaming?                                                                                                         | free text      |
| 19   | impact_mental_health| To what extent do you think that online body shaming can affect mental health (Examples: I feel anxious about how others may perceive my body, I have negative thoughts about my body, I have self-esteem issues) | rating        |
| 20   | impact_physical_health| To what extent do you think that online body shaming can affect physical health (Examples: I changed my eating habits, I started working out excessively, I make effort to change my appearance by using make-up) | rating |
| 21   | impact_social_behavior| To what extent do you think that online body shaming can affect social behaviour (Examples: I avoid eating in public, I dress differently, I use filters/ photoshop my photos, I avoid being photographed, I do body-checking more often) | rating |
| 22   | address_phenomenon | Do you think the phenomenon of online body shaming should be addressed?                                                                                                                   | single select  |
| 23   | social_do_enough   | Do you think social media platforms do enough to combat body shaming?                                                                                                                      | single select  |
| 24   | taken_stance       | Have you ever spoken out against online body shaming?                                                                                                                                      | single select  |
| 25   | who_turn_to        | Who do you think someone who experienced online body shaming should talk to for support?                                                                                                    | multi select *|
| 26   | what_actions_support| What actions do you think should be taken to support someone who experienced online body shaming?                                                                                          | multi select *|
| 27   | other_thoughts     | Would you like to share any thoughts or experiences related to this issue?                                                                                                                  | free text      |

*questions marked with an asterisk also included a free text "Other" option.

## Methodological Note

The patterns observed offer interesting insights, but should be understood as exploratory rather than confirmatory. In particular, we recommend not comparing country results with each other and always checking the sample size behind  the percentages.  Because of how the survey was sent out and because of its length, it is likely that the results are prone to selection bias, meaning the individuals who care most about the issue are also the ones who are most represented. This could explain, for example, the over-representation of female participants in our study. 

The Romanian survey stands out because of the marked presence of a male young demographic of university students (41% of respondents are male vs. an average of 27%; 86% of respondents are 15-18 vs. an average of 32%; 85% are studying in university vs. an average of 31%).  Because the Romanian survey also contains the most responses (165), its unique dynamics are impacting the overall results more than those of other countries.

For all these reasons, the analysis should be valued mostly not for its statistical relevance but because it revealed potential areas and angles that could be further assessed through larger studies or actions. More importantly, the surveys served as a means to actively engage young people with the issue, representing a valuable exercise in building awareness and self-reflection.
____
## Project funding
The Elephant Talk project is funded by the European Union. Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Education and Culture Executive Agency (EACEA). Neither the European Union nor EACEA can be held responsible for them.<br>
<img width="270" height="57" alt="eu" src="https://github.com/user-attachments/assets/42744d1a-e0b4-4d78-92d5-4a65c906c471" />
