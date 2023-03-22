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
git clone https://github.com/naeem123-cmd/Multi-lingual-Farmer-App

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























View Based Workflow

Go to Home Page Url - http://127.0.0.1:8000/ img.png

Click on Create User Link For New User Registration Url - http://127.0.0.1:8000/create-user-view/ img_1.png

Click on Login Button if already Registered Url - http://127.0.0.1:8000/accounts/login/ img_2.png

After Login Screen Redirected to Home img_3.png

Upload Farmer Data Page Url - http://127.0.0.1:8000/upload-view-auth/  img_4.png

Farmer Info Page Url - http://127.0.0.1:8000/info-view/{code} img_5.png

Note:  Some more pages you can explore on your own ....

Running Tests
Run tests
Run tests using command:

  coverage run --omit="/usr/*, /System/*" manage.py test
Converage Report (This will create a folder htmlcov and htmlcov/index.html contains Coverage Report)

  coverage html --omit="/usr/*, /System/*"
