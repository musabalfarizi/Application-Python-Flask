# Application-Python-Flask
Project Logical
![flask-crud-part-three](https://user-images.githubusercontent.com/17699469/76679750-6864bc00-6615-11ea-98c0-6375d583b0e5.jpg)
The complete code for my three-part tutorial, Build a CRUD Web App With Python and Flask, which you can find on Scotch.io [here](https://scotch.io/tutorials/build-a-crud-web-app-with-python-and-flask-part-three).
<br>
<br>
### Installation and Set Up

Prerequisites:

`Python 2`
<br>
`virtualenv`

### Clone the repo from GitHub:

`git clone https://github.com/andela-mnzomo/project-dream-team-three`
<br>
Create a virtual environment for the project and activate it:<br>
- virtualenv dream-team
- source dream-team/bin/activate <br>

### Install the required packages: <br>

- pip install -r requirements.txt
<br>

### Database configuration
You will need to create a MySQL user your terminal, as well as a MySQL database. Then, grant all privileges on your database to your user, like so:
<br>

`$ mysql -u root`
<br>
`mysql> CREATE USER 'dt_admin'@'localhost' IDENTIFIED BY 'dt2016';`
<br>
`mysql> CREATE DATABASE dreamteam_db;`
<br>
`mysql> GRANT ALL PRIVILEGES ON dreamteam_db . * TO 'dt_admin'@'localhost';`
<br>
<br>
Note that dt_admin is the database user and dt2016 is the user password. After creating the database, run migrations as follows:
<br>

`flask db migrate`
<br>
`flask db upgrade`
<br>

### instance/config.py file
<br>
Create a directory, instance, and in it create a config.py file. This file should contain configuration variables that should not be publicly shared, such as passwords and secret keys. The app requires you to have the following configuration variables:

`SECRET_KEY` <br>
`SQLALCHEMY_DATABASE_URI ('mysql://dt_admin:dt2016@localhost/dreamteam_db')`

<br>
<br>
Launching the Program
Set the FLASK_APP and FLASK_CONFIG variables as follows:

`export FLASK_APP=run.py`
<br>
`export FLASK_CONFIG=development`
<br>

You can now run the app with the following command: flask run

Testing
First, create a test database and grant all privileges on your test database to your user:

`$ mysql -u root`
<br>
`mysql> CREATE DATABASE dreamteam_test;`
<br>
`mysql> GRANT ALL PRIVILEGES ON dreamteam_test . * TO 'dt_admin'@'localhost';`
<br>
To test, run the following command: python tests.py
<br>

<br>

Built With...
<br>
### Flask
Credits and License
Copyright (c) 2020 Mus Ab Afarizi
<br>
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
<br>
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
<br>
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
