java cSEHH/SEHS2042 24-25 Semester One – Group Project 1 
 
SEHH/SEHS2042 Computer Programming 
Group Project – AI Service Token Management System 
(Due: 23:59, 1 Dec 2024, Sunday) 
 
Expected Learning Outcomes 
 
 develop computer programs in one or more high level language programming environment; 
 design and develop structured and documented computer programs; 
 explain the fundamentals of object-oriented programming and apply it in computer program 
development; 
 integrate the computer programming techniques to solve practical problems. 
 
Introduction 
 
In this assignment, you are going to develop an “AI Service Token Management System” that runs 
in the command line environment. The system maintains user records and manages the use of 
tokens by a user which can be used to pay for various web-based AI services. The system allows 
users to check their token balance and update their token balance upon purchasing new tokens or 
using a particular AI service. 
 
Tasks 
 
 Each group is required to write a Win32 Console Application program called TMS.cpp. 
 Each student is required to submit a video recording (at most 2-minute long) to demonstrate 
his/her individual contribution in the group project. 
 Each student is required to submit a Peer-to-Peer evaluation form (through the given Word file) 
via Blackboard. 
 
Program Requirements 
 
R0 When the program starts, the console should display a welcome message, followed by the 
Main Menu of the program. Users can enter the options of the corresponding actions (see 
R1 to R6 below). 
 
Welcome Message designed by your group 
*** Main Menu *** 
[1] Load Starting Data 
[2] Show User Records 
[3] Edit Users 
[4] Enter User View SEHH/SEHS2042 24-25 Semester One – Group Project 2 
 
[5] Show System Usage Summary 
[6] Credits and Exit 
***************** 
Option (1 - 6): 
 
R1 [1] Load Starting Data 
 
 When the user inputs 1 in the Main Menu, the system is loaded with starting data. The 
starting data includes user records as shown in R1.1 below. After the starting data is loaded, 
the system returns to the Main Menu. 
 
R1.1 The starting data to be loaded, together with the required data format of the data fields, are 
described below. 
 
 User records 
 
User ID Type Token Balance Auto Top-up 
SkyWalker T 20 N
Ocean123 T 35 N
Forest99 T 6 Y
Valley777 F 10 Y
Desert2022 F 25 N
River456 F 20 Y
Blaze2023 F 100 N
Meadow888 S 40 Y
Galaxy S 15 Y
Storm2024 S 30 N
 
 Data format of each field: 
 User ID: A string that uniquely identifies a user in the system (assume at most 50 
characters long); it is case-sensitive. You can assume it does not contain white space. 
 Type: A character (T, F or S) that represents the account type. Different restrictions 
about using the AI services, and different charging policies are used for different 
account types. See requirement R7 for details. 
 
Type (character) Rank (description) 
T Trial Account
F Full Account
S Student Account
 
 Token Balance: The token balance owned by the user. SEHH/SEHS2042 24-25 Semester One – Group Project 3 
 
 Auto Top-up: A character (Y or N) to indicate whether extra tokens would be 
purchased automatically if the token balance is not enough for a particular AI service. 
 
R1.2 Options 2 to 5 in the Main Menu are enabled only after the system is loaded with the 
starting data. If the user enters options 2 to 5 before starting data is loaded, an error message 
should be shown, and then the system returns to the Main Menu. 
 
R2 [2] Show User Records 
 
 [After the starting data is loaded] When the user inputs 2 in the Main Menu, the system 
displays all the fields of all user records. A tabular format should be displayed, and the 
records are sorted in alphabetical order based on the ID values. Data shown should be 
the latest set of data since the starting data is loaded (updates on the user records resulted 
by the operations under options 3 or 4 in the Main Menu should be included). After 
showing the records, the system returns to the Main Menu. 
 
R3 [3] Edit Users 
 
[After the starting data is loaded] When the user inputs 3 in the Main Menu, the system 
prompts for the next user input of a User ID. If such User ID does not exist in the system, 
it is an add user operation. Otherwise, it is a delete user operation. 
 
You can assume the system will store at most 100 user records. 
 
Add user 
The system asks the user to input the information of the remaining three fields: (1) Type, 
(2) Token Balance, and (3) Auto Top-up. After getting all user inputs, the new user should 
be added into the system. For any invalid inputs (e.g., wrong field values, incorrect range 
for token balance, etc.), the system allows TWO more retries. With more than THREE 
times of invalid inputs, no user is added. The system prints an appropriate error message 
and returns to the Main Menu. 
 
Delete customer 
The system displays the information of the user (including all the fields), and prompts for 
user’s “Yes/No” confirmation on the delete operation. The user record is deleted from the 
system if it is confirmed. 
 
A message showing the summary of the above operation is then displayed, and the system 
returns to the Main Menu. 
 SEHH/SEHS2042 24-25 Semester One – Group Project 4 
 
R4 [4] Enter User View 
 
[After the starting data is loaded] When the user inputs 4 in the Main Menu, the system 
prompts for the next user input of a User ID. If such User ID does not exist in the system, 
the system displays an error message and returns to the Main Menu. Otherwise, it displays 
the User View Menu as shown below and allows further processing on the particular user 
(e.g., River456) as follows (see R4.1 to R4.4 below). 
 
Action for User ID: River456 
***** User View Menu ***** 
[1] Select AI Service 
[2] Purchase Tokens 
[3] Edit Profile 
[4] Show Transaction History 
[5] Return to Main Menu 
************************** 
Option (1 - 5): 
 
R4.1 [1] Select AI Service (Also refer to requirement R7 about the AI services) 
 
 When such option is chosen, the system shows the list of available AI services and asks 
user for the choice. After the choice input, the system accepts subsequent user inputs 
associated with the chosen AI service. If all user inputs are valid, the AI service is allowed 
for that user, and the user’s token balance is enough for paying the AI service, the user’s 
token balance will be updated accordingly. 
 
 The user can still use the AI service with “less-than-required” tokens in his balance if the 
“Auto Top-up” option is enabled for the user account. If so, the system should additionally 
display the extra money that has be代 写SEHS2042、C++
代做程序编程语言en paid for buying the extra tokens, and the user’s final 
token balance. The auto top-up amount should be in a multiple of $20, which buys 
minimum extra tokens that are enough for the AI service. 
 
 The AI service will not be paid if it is not allowed for that user, if there is any invalid user 
input, or if the user’s token balance is insufficient with “Auto Top-up” option disabled. In 
such siutation, no change in the token balance will be made. 
 
 For all the above cases, the system should print a meaningful message about the situation, 
print the change in user’s token balance as a result, and return to the User View Menu. 
 
 
 SEHH/SEHS2042 24-25 Semester One – Group Project 5 
 
R4.2 [2] Purchase Tokens 
 
 Each token costs $2. When such option is chosen, the system prompts for user input of an 
even integer value, which is the amount of money to spend for purchasing tokens. The 
system then calculates and adds the tokens into the token balance for the user. For any 
invalid input, no tokens should be purchased. 
 
R4.3 [3] Edit Profile 
 
 When such option is chosen, the system allows users to make changes to either the 
“Account Type” or the “Auto Top-up” setting. User is allowed to choose which fields he 
wants to update, and to input the new field value. The user’s profile should be updated 
afterwards, if user inputs are valid. 
 
 For any invalid input, the system allows TWO more retries. With more than THREE 
rounds of invalid inputs, the system prints an appropriate error message and returns to the 
User View Menu. 
 
R4.4 [4] Show Transaction History 
 
 When such option is chosen, the system displays all token transaction records history for 
the particular user since the program starts running: 
 
 All kinds of tokens transactions under R4.1 and R4.2 should be considered and 
displayed. 
 The transaction records should be displayed in the order that they were carried out. 
 For token transactions under R4.1 (paying for an AI service), both the number of tokens 
spent and the name of the AI service being used should be displayed. If there is an “auto 
top-up” action, the extra money paid for buying the extra tokens should be displayed 
too. 
 For token transactions under R4.2 (purchasing tokens), both the number of tokens 
purchased and the amount of money spent should be displayed. 
 At the end, a summary showing the original token balance, the final token balance, the 
change in token balance, and the TOTAL amount of money paid for buying tokens 
(including those used under “auto top-up”) should be displayed. 
 A meaningful message should be shown if there have been no transactions made so far 
for the user. 
 
 After displaying the transaction history, the system returns to the User View Menu. 
 SEHH/SEHS2042 24-25 Semester One – Group Project 6 
 
R4.5 [5] Return to Main Menu 
 
 When such option is chosen, the system returns to the Main Menu. 
 
R4.6 Stay at the User View Menu 
 
 Following R4.1, R4.2 and R4.3, after an operation for a user, the system should display the 
change (the original and the new values) in the token balance or the profile of the user by 
that operation, and then stays at the User View Menu. 
 
R5 [5] Show System Usage Summary 
 
[After the starting data is loaded] When the user inputs 5 in the Main Menu, the system 
displays the usage summary of the system since the program starts running. The summary 
includes: (1) the number of tokens spent on each of the AI service by all users, (2) the total 
number of tokens spent on all AI services by all users, and (3) the total amount of money 
paid for buying tokens (including those used under “auto top-up”) by all users. 
 
After displaying the system usage summary, the system returns to the Main Menu. 
 
R6 [6] Credits and Exit 
 
 When the user inputs this option, the system prompts for user’s confirmation. If the user 
inputs ‘n’ or ‘N’, the system returns to the Main Menu. If the user inputs ‘y’ or ‘Y’, the 
system displays the personal particulars (student name, student ID, tutorial group) of the 
group members and terminates. Other input is not acceptable and the system should ask 
the user to confirm again. 
 
R7 Description about AI services 
 
 A user can select an AI service and pay for it using tokens under R4. Each token costs $2. 
There are four AI services. Charges of different AI services are put down below, which 
also takes the user type into consideration: 
 
 (1) Image Recognition 
Charging Model: Based on image size 
Image Size Charges (per image) 
Trial Account Full Account Student Account
Under 3 MB 5 tokens 5 tokens 4 tokens 
Over 3 MB Not allowed 8 tokens 7 tokens 
 SEHH/SEHS2042 24-25 Semester One – Group Project 7 
 
(2) Speech-to-text transcription 
Charging Model: Based on the length of the speech audio file 
(same charge for all user types) 
Length of Audio Charges (per minute) 
The first 3 minutes 2 tokens
After 3 minutes 3 tokens
 
 (3) Predictive Analysis 
Charging Model: 10 tokens per prediction task (same charge for all user types) 
 
 (4) Natural Language Processing (NLP) 
Charging Model: Based on length of text for NLP, 1 token for every 500 characters 
(e.g., a 900-character text needs 2 tokens) 
Note: For trial account, the length of text should not exceed 2500 characters. If so, the 
AI service should not be used. 
 
 As a result, for each AI service, the required user inputs for charge calculation are: 
AI Service Required user inputs for charge 
calculation 
(1) Image Recognition Size of the image (in MB) 
(2) Speech-to-text transcription Length of speech audio file (in minutes)
(3) Predictive Analysis Number of prediction tasks 
(4) Natural Language Processing (NLP) Number of characters in the text 
 
R8 Suitable checking on user’s input is expected, except in situations with assumptions stated 
in the requirements above. Appropriate error messages should be printed whenever 
unexpected situation happens, e.g., input value out of range, incorrect character input, etc. 
 
R9 The use of functions (in addition to main function) and classes (i.e., OOP design) are 
expected in your program. Appropriate comments should be added in your source code file. 
 
R10 Creativity and Critical Thinking: Use suitable format to present all required information of 
users and AI services clearly and neatly. Additional features can be added. 
 
Tips 
 
1. To handle unexpected input error (e.g. input a character to an integer variable), you may use 
the following code appropriately in your program: 
cin.ignore(); // Discard the content in the input sequence. 
cin.clear(); // Reset the input error status to no error. 
 
         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
