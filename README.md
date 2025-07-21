# The Elephant Talk project
Elephant Talk is a youth active citizenship project created by Maghweb in collaboration with Impact Hub Labs, Polylogos and Young Educators funded by the EACEA in the CERV programme, Citizen’s Engagement and Participation strand. The project aims to engage young citizens across Europe in a collective, international collaborative data gathering and visualisation action against online gender-based hate speech with youth workers from their different communities. 

**This repo contains the data collected through the Elephant Talk survey that ran until April 30th, 2025**. The survey has been administered through the open-source and GDPR-compliant platform [FormBricks](https://formbricks.com/). The survey was sent in 8 different language versions: Catalan, Croatian, Greek, Italian, Portuguese, Romanian, Slovenian, and Spanish. A total of 1.395 respondents began the survey, of which 706 (51%) completed all questions. The process of combining the 8 survey response files, one for each language, in a single cleaned English file has been achieved with a mix of Python, manual data cleaning, and assistance from Claude.ai, as detailed in the "Data Cleaning Documentation" file.

👉 See full survey results: [stophatespeech.eu](www.stophatespeech.eu)

### In this repo you will find:

#### RESULT FILES
- The raw data files: one file for each language result, as outputted by FormBricks on April 30th, 2025.
- The combined and translated result file; WIDE FORMAT: In this file, all language responses from the 8 files are combined, and each question contains both the original response and the translated response (with the suffix "_EN" in the column name. Multiple choice answers are separated by a pipe character ("|")
- The combined and translated result file; LONG FORMAT: In this file, there is one row for each response (english translation) given by each participant to each question.

#### META
- Documentation of the data cleaning process
- Question dictionary: .csv file with the English translation and the original text of all the questions contained in the survey
- Answer dictionary: .csv file with the English translation and the original text of all the answers contained in the survey, including free text answers

**Example of contents:**

*<img width="894" height="321" alt="wide" src="https://github.com/user-attachments/assets/58099ce4-ef47-44c4-b51c-36f798042bf3" /><br>
*The result file, wide format*
<br>
<br>
<img width="349" height="247" alt="long" src="https://github.com/user-attachments/assets/90d19a8d-2642-4d6e-a29a-2c0c18b418e3" /><br>
*The result file, wide format*
<br>
<br>
<img width="1280" height="291" alt="q_dict" src="https://github.com/user-attachments/assets/9f6dca77-57aa-4262-835e-a8378dbd4485" /><br>
*The question dictionary file*
<br>
<br>
<img width="865" height="299" alt="a_dict" src="https://github.com/user-attachments/assets/a2439e79-f158-4853-b77d-f473db25ed5d" /><br>
*The answer dictionary file*
