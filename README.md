# Backend-Rest-API
This guide outlines the steps to deploy a Python/Django REST API on an Ubuntu 24 server using Gunicorn.


VIRTUAL Machine for Database and Backend

React-Django-App


# PostgreSQL Deployment on Ubuntu 24

This guide outlines the steps to deploy a PostgreSQL database on an Ubuntu 24 server.

1. Update System Packages

bash
sudo apt update


2. Install PostgreSQL

bash
sudo apt install postgresql -y


3. Verify PostgreSQL Service (Optional)

bash
sudo systemctl status postgresql


4. Access PostgreSQL Shell and Configure Database

bash
sudo -u postgres psql


Execute the following SQL commands:

sql
-- Create the database
CREATE DATABASE computex;

-- Create the user and set the password
CREATE USER admin WITH ENCRYPTED PASSWORD '12345';

-- Change the database owner to admin
ALTER DATABASE computex OWNER TO admin;

-- Grant all privileges to the user for the database
GRANT ALL PRIVILEGES ON DATABASE computex TO admin;

-- List databases (optional)
\l

-- Change password of an existing user (if applicable)
ALTER USER postgres WITH PASSWORD '123456';

-- Exit PostgreSQL shell
\q





# Deploy a Python/Django REST API on Ubuntu 24 with Gunicorn

This guide outlines the steps to deploy a Python/Django REST API on an Ubuntu 24 server using Gunicorn.

1. Update System Packages

bash
sudo apt update


2. Install Pip and Python Virtual Environment Package

bash
sudo apt install python3-pip python3-virtualenv -y


3. Create and Activate Virtual Environment

bash
python3 -m virtualenv venv
source venv/bin/activate


4. Clone the Project

bash
git clone https://github.com/Ochubaanthony/React-Django-App.git
cd React-Django-App


5. Install Dependencies

bash
pip install --upgrade setuptools
pip install -r requirements.txt

NEXT 
Ls
cd Computex



6. Configure Database

Ensure your database connection is properly configured in the Django settings

7. Run Migrations

bash
python manage.py migrate


8. Run Application with Gunicorn

bash
gunicorn --bind 0.0.0.0:8000 Computex.wsgi:application


9. Verify Deployment

Open a web browser and navigate and enter just the IP without the port 8000



THEN GO TO THE PAGE 


 Verify Deployment

Open a web browser and navigate to your server’s IP address or domain name. Your React site should now be live and accessible


GO TO AZURE PORTAL TO OPEN THE INBOUND RULES AND OUTBOUND RULES
Step
Add IP address of frontend on the backend port inbound
Add the densitnation port 8000
Add port 443
Add Port 22
Add Port 80
Add port 8080
Add port 8000
Add Port 8000 with the Frontend IP Address

Repeat the same on Backend
Add IP address of Backend on the frontend inbound
Add the destination port 8000


Notice at the backend all the data send out are recorded .
