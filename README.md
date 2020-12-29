## Auto-mailing responses from Google Sheet


This repository contains code for auto-mailing any responses from a google sheet. This one in particular caters to COL215 minor response mailing to individual students. 

### Extracting e-mails from entry number 
Before that, these steps need to be followed to extract e-mails out of entry numbers:
  1. Make two extra columns (possibly C and D) beside the entry number column (Column B, Column A probably is time-stamp), fill one whole column (Column C) with @iitd.ac.in.  
  2. Find and replace 2019CS1 and 2019CS5 with CS119 and CS519 respectively. This is affect the entry number column (possibly in column 'B'). For the rest of few students of other department/year, it'll take few seconds to change that manually.
  3. In the first D cell, if it's D2 write B2&C2 and drag it to the whole column. Now, we got the emails of all the students. 
  4. Copy (Ctrl+C) and paste by value (Ctrl+Shift+V) the e-mails in an 'e-mail column' and re-paste entry numbers from an older sheet in the entry number column. Delete other redundant columns. Now we have time-stamps in A, Entry number in B, E-mail in C, Names in D and all other data in other columns.
  
### Usage

Run the following pip command to get the Google OAuth library.
```
pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

Run main.py after installing the OAuth Google libraries using the following command:
```
python main.py
```

A window will open where you will have to login to the google account through which you'll mail and where the data is saved in google sheets. After that it will auto update and mail the students.
Please do not share the pickle file generated after logging in as it will cause breach of security.

You can change the email text by simply changing email.txt and using the appropriate template tags.
