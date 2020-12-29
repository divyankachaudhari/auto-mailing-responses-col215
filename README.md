## Auto-mailing responses from Google Sheet


This repository contains code for auto-mailing any responses from a google sheet. This one in particular caters to COL215 minor response mailing to individual students. 

Note: All the actions need to be done from the same Google account. If you have multiple accounts, you can try doing it in icongnito mode so that you work with only one account at a time. Possibly make a new account for running this. For this repository and make the changes as given below.

### Extracting e-mails from entry number 
Before that, these steps need to be followed to extract e-mails out of entry numbers:
  1. Make two extra columns (possibly C and D) beside the entry number column (Column B, Column A probably is time-stamp), fill one whole column (Column C) with @iitd.ac.in.  
  2. Find and replace 2019CS1 and 2019CS5 with CS119 and CS519 respectively. This is affect the entry number column (possibly in column 'B'). For the rest of few students of other department/year, it'll take few seconds to change that manually.
  3. In the first D cell, if it's D2 write B2&C2 and drag it to the whole column. Now, we got the emails of all the students. 
  4. Copy (Ctrl+C) and paste by value (Ctrl+Shift+V) the e-mails in an 'e-mail column' and re-paste entry numbers from an older sheet in the entry number column. Delete other redundant columns. Now we have time-stamps in A, Entry number in B, E-mail in C, Names in D and all other data in other columns until column R. Do not leave any column blank.
  
### Editing the code

1. On line 12, insert spreadsheet ID (google what it is) of the spreadsheet where all responses are stored.  
2. On line 66, insert Sheet name (each sheet has a name).
3. On line 106, insert your gmail address. Use the same account as the google sheet account.

### Google sheets API
1. Go to https://developers.google.com/sheets/api/quickstart/python.
2. Click on enable the Google Sheets API.
3. Continue with default project name and select desktop app and create.
4. Click on download client configuration. That's your credentials.json file. Upload it to your forked repository (make sure to delete the one in this repository first, it's mine). 
5. Go to https://console.developers.google.com/apis/api/gmail.googleapis.com/ and enable GMail API. 

### Usage

Run the following pip command to get the Google OAuth library.
```
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```
or use pip3 if that's installed instead of pip. 

Download the repository and extract it. Go to the location of the folder in the terminal and run the following command after installing the OAuth Google libraries:
```
python main.py
```
or use python3 instead of python if that's installed. 

A window will open where you will have to login to the google account through which you'll mail and where the data is saved in google sheets. After that it will auto update and mail the students. Please do not share the pickle file generated after logging in as it will cause breach of security.

You can change the email text by simply changing email.txt and using the appropriate template tags. I have made a default text file which I feel is approppriate and doesn't need changing. 

I have tried running the code on a sheet while resembles the google form responses we had been given and it works. 
