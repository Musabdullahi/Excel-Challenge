

# *Excel Challenge*  
---------------------------------
You have been provided with a dataset (https://docs.google.com/spreadsheets/u/0/d/1aBAVHr0DXMuJHcEdxWbp6NCMdc9cWa7S/htmlview) containing registration information for participants of a training program.    
  
The challenge is to create an Excel solution that will dynamically update additional fields as new data is added to the dataset.

## Case Brief: Excel Data Transformation   
The dataset includes the following fields:  
• Full name (which contains title, first name, 2nd name, and 3rd name)  
•	DOB (Date of Birth)  
•	Registration Date  
•	Skill  
   
 ### The challenge is to create an Excel solution that will dynamically update additional fields as new data is added to the dataset. The additional fields to be generated are as follows:  
•	Title: Extract the title from the "Full name" field.  
•	Initials: Create initials from the first letter of the first name, second name.  
•	Last Name: Extract the last name from the "Full name" field.  
•	Full name Short: Create a shortened version of the "Full name" field.  
•	Age: Calculate the age based on the "DOB" field.  
•	Age Group: Group participants into different age groups of 0-30, 31-40, 41-50, overage.  
•	Reg ID: Generate a unique registration ID for each participant in the format TR-YY-XXX  
     o	TR stands for training (everyone have this),  
     o	YY would be GD, IF, MG, AL, LW, PG & MT for graphics design, influencer, Manager, Analyst, lawyer, programming & Marketing respectively.  
     o	XXX stands for the rank of the participant by date and time, the first participant to register would have a rank of 001.  

### Challenge Requirements:  
Your Excel solution should be designed to handle new data entries. As new rows of registration data are added to the dataset, the additional fields should be updated automatically.  


## Case Report Solution
Each column is labelled as:  
Fullname: name entered by trainee  
DOB: date of birth. (Displayed as dd/mm/yyyy)  
Reg Date: date of registration (Displayed as dd/mm/yyyy)  
Time Registered: time of registration   
Skill: the skill to be learnt (Marketing, Programming, graphic design, manager, analyst, lawyer, influencer)  
FullName1: the Fullname column is cleaned using the formula =PROPER(TRIM(CLEAN(A2)))  
FullName Clean: the FullName1 column is cleaned to remove fullstop (.) after abbreviation using =SUBSTITUTE(F2,".","")  
1st Space: serves as indication delimeter based on first space using the formula =Find(“ “)  
2nd space: serves as indication delimeter based on second space using the formula =Find(“ “)  
3rd space: serves as indication delimeter based on third space using the formula =Find(“ “)  
Title: indicates trainees title (Mr, Mrs, Dr) extracted using the =left() and 1st space formula  
Initials: indicates the first letter of trainees first name and second name extracted using the =left & Mid() formula and the spaces delimiter.  
Last Name: indicates Trainees last name extracted using the =Right() formula and the 3rd space delimiter.  
Shortened form: indicates trainees initials with last name extracted using the =Concatenate() function.  
Age: trainees age based on DOB using the =YEAR(TODAY())-YEAR(B2)) formula.  
Age group: assigned using the =Ifs formula as (0-30, 31-40, 41-50, overage).  
S/N0.: Assigned used the =Row function based on the date and time of registration.  
ID: Formulated using the combination of =concatenate & Xlookup function based on the template (TR-YY-XXX).  



