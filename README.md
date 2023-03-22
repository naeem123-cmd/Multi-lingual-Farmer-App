# Multi-lingual-Farmer-App
A web application that helps us convert farmer details from English to different languages.

Tech Stack Used

Backend for API - Django RestFramework
Frontend - Django | Django Template language | HTML | CSS
Database - SQLite

Steps To Set Up

System Requirements Assumptions
OS: Linux
Python Version: 3.8
Package Installer: pip3
python3-virtualenv
Other Steps
Pull the GitHub repo

git clone https://github.com/nitesh18400/FarmerApp.git
Enter the repo root directory

cd FarmerApp/
Create a python virtual environment using command

virtualenv venv
Activate the environment using the command

 source venv/bin/Activate
Install the dependencies specified in requirement.txt by using the command

pip3 install -r requirement.txt
Enter the FarmerApp directory

 cd FarmerApp/
Rename credentials.json to credential-sample.json after Completing These Credentials

"DEBUG": "",
"ENVIRONMENT": "",
"GOOGLE_API_KEY": {},
"DJANGO_SECRET_KEY": ""
Database setup

 python3 manage.py makemigrations
 python3 manage.py migrate
Run the command.

 python3 manage.py runserver
The site should be live at base url - 127.0.0.1:8000.

APIs Workflow
Note: You can Test these APIs using Postman or By using Any Browser (Logged in Session for Authenticated APIs)

- Create User
Description: Create New User
Url - http://127.0.0.1:8000/create-user/
Post Data - {'Username': 'Your_Username', 'Password': 'Your_Password' } type - FormData
- Token Generation
Description: Generate Token for APIs Authorization
Url - http://127.0.0.1:8000/create-user/token-auth/
Post Data - {'Username': 'Your_Username', 'Password': 'Your_Password' } type - FormData
- Authentication-driven APIs
1. FARMER INFORMATION
Description: Get language specific information of all the farmers in json format.
Url - http://127.0.0.1:8000/info-auth/?lang={code}
Custom Headers - {'Authorization' : 'Token TokenValue'}
2. Upload Farmer Data Information File
Description: Upload Csv File Consist of Farmer in a Specified Format
Url - http://127.0.0.1:8000/upload_auth/
Custom Headers - {'Authorization' : 'Token TokenValue'}
Post Data - {'file_uploaded': 'your_csv_data_file'} type - FormData(Files)
Assumption - Uploaded File should be of correct Format
- Non-Authentication-driven APIs
1. FARMER INFORMATION
Description: Get language specific information of all the farmers in json format.
Url - http://127.0.0.1:8000/info/?lang={code}
2. Upload Farmer Data Information File
Description: Upload Csv File Consist of Farmer in a Specified Format
Url - http://127.0.0.1:8000/upload/
Post Data - {'file_uploaded': 'your_csv_data_file'} type - FormData(Files)
Assumption - Uploaded File should be of correct Format
