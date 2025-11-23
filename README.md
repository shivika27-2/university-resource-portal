# university-resource-portal
🎓 University Resource Management Portal (URMP)
Shivika Patidar / 25BAI11010 

# Project Overview (What it does)
The URMP is basically a website we built to make booking university stuff way easier. Think of it like a common online calendar for everything we share on campus—lab equipment, study rooms, or even specific library books.

Our main goals were:

1.Stop booking clashes (no more two people showing up for the same room!).

2.Let students and staff see what's free right now.

3.Help administrators track how much everything is being used.

# Features (The cool things it can do)
The Big 3 Functional Modules:
Users & Roles: We have secure logins for three types of people:

1.1 Admins: They can add new resources (like a new camera) and manage everyone's accounts.

1.2 Faculty: They can book resources for their classes or research.

1.3 Students: They can check availability and reserve things they need.

Easy Booking: Users can search for a resource, see a calendar to check free slots in real-time, and make a reservation. The system automatically checks for conflicts!

Usage Reports: Admins can pull reports (as PDF or CSV) to see which resources are the most popular, when peak booking times are, and who is frequently using what.

Non-Functional (How well it works):
Security: Your data is safe! We use secure logins and check permissions for every action (e.g., only an Admin can delete a resource).

Usability: It's designed to be super simple to use, whether you're on a laptop or your mobile phone.

Reliability: The booking system uses a strict database setup to guarantee that once you book something, no one else can book it simultaneously—data is always correct.

Performance: Searching for resources and loading your dashboard is fast—it should load in under 3 seconds.

# Tech Stack (The tools we used)
The URMP is powered by a robust and reliable set of technologies, chosen for their efficiency and stability:

Backend (The Brain): Python (Django)

We used Python's powerful Django framework. This choice helps us handle all the complex logic, user accounts, and database interactions using a clean, all-Python codebase, ensuring rapid and secure development.

Database (The Storage): PostgreSQL

PostgreSQL serves as our primary database. It's a highly reliable, enterprise-grade system, which is crucial for maintaining the accuracy and integrity of our booking transactions and preventing simultaneous booking errors.

Frontend (What you see): Django Templates & Tailwind CSS

The user interface is built using standard Django HTML Templates. Styling is managed with Tailwind CSS, a utility-first framework that ensures the website looks professional and is fully responsive across all screen sizes (laptop, tablet, and mobile).

Version Control: Git & GitHub

Git and GitHub were essential throughout the development process for tracking all changes, managing different feature versions, and facilitating smooth collaboration on the code.

Setup Guide (How to run it yourself)
This assumes you have Python 3.x and PostgreSQL installed.

1. Get the Code
Go to your terminal/command prompt and download the project:
git clone [https://github.com/](https://github.com/)[Your-GitHub-Username]/university-resource-portal.git
cd university-resource-portal
2. Prepare Python
Create an isolated environment (so it doesn't mess with your other Python projects) and turn it on:
pip install -r requirements.txt
. Install Required Packages
Install all the necessary libraries the project needs:

Bash
pip install -r requirements.txt
4. Set up the Database
Make sure your PostgreSQL server is running.

Create an empty database named resource_db.

Create a file named .env in the main project folder and add your database login details (like your username and password).

5. Run the Initial Setup
This command sets up the database tables and creates your first admin user:

Bash
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser  # Create your admin login here
6. Start the Website!
Launch the development server:

Bash

python manage.py runserver
Open your web browser and go to: http://127.0.0.1:8000/

# Testing Instructions (How to check if it works)
We need to check the logic is perfect, especially for bookings!

1. Run Automatic Tests:
Use this command to run all the small tests written in the code:

Bash
python manage.py test
2. Manual Check (Try these!):
->Log in as the Admin and try to add, edit, and delete a piece of equipment.

->Log in as a Student and try to book a room. Then, quickly try to book the same room for the exact same time with a different student account. The second booking should be blocked!

->Generate a usage report to confirm all data is being counted correctly
