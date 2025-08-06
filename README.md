Welcome to Password Manager:

Features: This password manager  be able to handle different users and store their usernames and passwords for websites.

    store  username & password for a website it should store the username, the password, the website name, the website URL, date created, date last updated

The user should  be able to store to add, edit & delete passwords stored in the application.

The user should be able to view the login’s currently stored, however the password should be hidden, but the user can choose to show the password in plain text.

All passwords should be encrypted and stored in a database or text file. The application should also be able to decrypt the encrypted password to show the original in plain text.

The users should be able to search for passwords by the name of the website 

The user should be able to sort the passwords by the last updated date.

When adding a new password, the application should provide an option to generate a random password.

Users should be able to login with a username and password, and they should only be able to see the passwords that they have created. There will be an admin login, that will be able to see all passwords for all users and be able to edit & delete them.

Requirements to run this app:

    Python 3.8+
    Virtualenv
    PostgreSQL

How to run this app: Clone this repository and enter the folder. Create a virtual environment in windows like this:

virtualenv myenv

You need to activate virtual env:

myenv\Scripts\activate
create a virtual environment in kali like this 
python -m venv myenv
to activate it 
source myenv/bin/activate

Now run this command in the terminal to install the required libraries:

pip install -r requirements.txt

Now copy and paste .env.sample inside the core app as .env and add all the credentials like your app secret key, DB information and ENCRYPT_KEY. To generate ENCRYPT_KEY , run this command in the terminal:

from cryptography.fernet import Fernet
Fernet.generate_key()

This will generate ENCRYPT_KEY. Now migrate the DB:

python manage.py makemigrations
python manage.py migrate

Now run:

python manage.py runserver

and navigate to http://127.0.0.1:8000/ in your web browser.

For admin panel, first create a superuser:

python manage.py createsuperuser
