Phase IV: Software Testing 

Marsia Mustafa 

A website for ‘Physiotherapie Dinaj’ 


For this phase, I have decided to analyze two of the main elements of my website that require user input: sign-up and log in form. 

Below I have developed 2 test cases for the sign-up form on my website.  

Test Case Description: How does the system react when a user uses the same email to sign-up 

Test steps: 

Navigate to the sign-up page 

Fill in the required fields (Username, Email, Password, Repeat password) 

Click Submit  

Do the same thing all over and try to use the same email as in the first case 

Expected results: 

The user receives an error message: “Email already taken” 

The user cannot further continue without using another email to sign-up 

 ****image***** 

Above is the condition from the ‘Process-Sign up’ file that states that if there is a duplicate entry in the database (1062 number), the user will receive an error message that stops him from accessing further components of the webpage. This condition checks whether the email entered already exists in the ‘Sign-up’ table in the respective database in PhpMyAdmin. 

The aim of this testing is to make sure that the security of the user is accomplished and that no mistakes can be made while signing up. 


 

Test Case Description: How does the system respond if the password does not fulfill the requirements 

Test steps: 

Navigate to the sign-up page 

Fill in the required fields (Username, Email, Password, Repeat password) 

In the email section, enter a password that is less than 8 characters, does not contain at least one letter and one number 

Click Submit 

Expected results: 

The user receives error messages for each scenario of inputting a password. 

 ****image*****

In this code, there are stated three conditions where each is responsible for three possible scenarios while entering a password: less than 8 characters, no letter, no number. Even if only one of the above conditions is not fulfilled, the user cannot continue further with the sign-up process. 

The aim of this testing is to make sure that the password entered is strong and secure. In this way, the user can feel much safer while navigation through the website. 




Below I have developed a PHPUnit test for the php script named ‘process-signup.php’. I have focused on testing the validation rules and the database interaction. 

The setUp method initializes the database connection before each test is applied. 

The tearDown method closes the database connection after each test. 

The testValidRegistration method tests a valid registration by providing valid input data and checks if the script redirects to the success page. 

The testInvalidEmail method tests an invalid email input with no right syntax and checks if the error message contains "Valid email is required".  

 ****image*****

This testing script focuses on the invalid email entered scenario. 

 

 

 

Below I have developed one test case for the ‘log in’ form on my website. 

Test Case Description: How does the system react when a user tries to login in without signing up in advance 

Test steps: 

Navigate to the login page 

Fill in the required fields (Email, Password) 

Click Submit  

Expected results: 

The user cannot further continue without primarily signing up. 

 ****image*****

This PHP code script checks the availability of an email address in a database table called "user". If the email entered is not already part of the database table where the data from the sign-up form is stored, the user cannot log in. 

The aim of this testing is to make sure that the system works chronologically. In other words, making sure that before logging in, the user must primarily create an account. 


 

Below I have developed a PHPUnit test for the php script named ‘validate-email.php’. I have focused on testing the validation rules and the database interaction. 

****image*****
The setUp method initializes the database connection before each test. 

The tearDown method closes the database connection after each test. 

The testEmailAvailable method tests the case when the email is available in the database. 

The testEmailNotAvailable method tests the case when the email is already taken in the database. 

This testing script focuses on how the system reacts to a user trying to login in without signing up. 

 
***********************************
 

Phase III: Software Design and Modeling 

Deadline: April 1st, 2024, 23:59 

Marsia Mustafa 

 

System Architecture 

The contact us form 

For more questions, every client can leave their phone number or email address so they can be reached by the clinic staff later. This data will be stored in the respective database in PhpMyAdmin. 

Signup form 

Here, the clients can create the new accounts they want to use for further services by the clinic. This data will be stored in the respective database in PhpMyAdmin. I have thought of developing a form organized into a table with questions to be completed by the clients online a can be sent to the clinic email. I am also working on developing an appointment schedule by using Google calendar as a tool. 

The footer 

Every page in my website will have a common footer which contains three extra links: 

Leave us a google review: this link connects the patient with a google form review where they can type in their experience 

You can find us here: this link gives the patients the possibility to connect with the location of the clinic in Google Maps 

Take a closer look: by clicking this, the patients will be redirected to the clinic photos uploaded by the staff in Google 

The footer will also contain the telephone number of the clinic also the email which clients can use to reach out the staff for any question 


Component Diagram 

Below a have created a component diagram for the signup form I want to include in my website: 

THE USER INTERFACE --> THE WEB SERVER --> THE BACK-END LANGUAGE --> DATABASE 

The user interface will be a sign-up form developed using html and CSS which will give the patient the possibility to enter their name, surname, email address and their password twice. 

The web server will be the Apache HTTP Server that is part of the XAMPP program which handles the HTTP request and response. 

The back-end language I am using to handle this submission of data is PHP language. 

The data will be stored in PhpMyAdmin. 

Database design 

My website stores the patients’ data into two different databases.  

The first one is the database which has 5 attributes: Name, Surname, Email, Phone and ‘Your Message’. All these fields are mandatory to be completed and will be saved into the Contact Us database in PhpMyAdmin. 

The second database is the one that stores the data gathered from the Sign-up form. It includes these attributes: Name, Email, Password and repeated password. The email will be the primary key of the table and every time a new patient wants to sign up with a primarily used password, the website generates an error message. Also, the password will be saved as a string of characters by using the password hashing method to provide security for the patients. 

 

Use case diagram 

Fill in the sign-up form --> Fill in the question form for the patients --> Send the table form via email to the clinic 

This use case diagram shows how the patients can reach the question form and send it so it can be further studied by the staff of the clinic. 

I am currently working on the idea of how to make the appointment scheduling system by using google calendar as a tool. I am thinking of using also the CRUD operations to give the patients the possibility to choose and remove an appointment.  

I am trying to make the website dynamic, so it is easy to navigate by implementing buttons and extra links that help patients reach out new pages.  
**************************************************************************************************************************

Marsia Mustafa 

Phase II: User Requirements and Application Specifications 

1. Chosen Development Model: 

For this project, I have chosen to develop my product using the Agile model. The reason behind this is the fact that the business I am working with is a new one in its field. This makes their current requirements not clear and stable. For the moment they are only looking for a website showing an overall view of the clinic’s services. Their involvement is highly needed since they provide new system requirements regularly.  This involves keeping track of what they want to be done, changed or added.  

2. User requirements: 

The stakeholders of this project are the two owners of the clinic. Their requirements as users are: 

The website should present all services provided by the clinic, a general information plus a photo-gallery of the work environment 

A new costumer should have a form where he can type his personal data and this data can be gathered in a database so the staff can call them later 

A sign-in form for clients to complete and for them to send a form with questions needed before they start their therapy 


3. Functional requirements: 

The end-users will be able to create accounts after they register as patients 

The website will provide detailed information about the physiotherapy services offered, including types of treatments, specialties, and pricing 

Provide a clear contact information section, including phone numbers, email addresses, and a contact form 

Save the data gathered by the patients into respectively databases 

 

4. Non-functional requirements: 

User’s login password will be encrypted during storage in the database 

The website should be easy to navigate, with intuitive menus and clear calls to action 

The website should be compatible with popular web browsers 

 

5. Application Specifications: 

I am thinking of creating 4-5 interior pages for my website as described below: 

Home: General information about the history of the clinic, their opening time and some photos form the work environment 

Services: A page which will show all the services provided by the clinic and their respective prices 

Sign-up: A patient must sign up and complete a form which contains question so that the staff finds the best treatment for them 

Contact-us: This page will contain a form for users that need a more detailed information about the overall clinic 

 

Database model: 

I will be using two databases in my website to save two different types of data: 

Data from clients which want a more detailed information about the clinic 

Data gathered from sign up form for clients who are ready for an appointment 

This data will be saved into databases in PhpMyAdmin where each isn't correlated.  

Security measures: 

For the security requirements I have thought of implementing one or both of the below alternatives: 

Strong password policies for the sign-up user form 

Limited login attempts 

Based on how I am going to develop this sign in/up form and what its usage will be, I will decide which alternative will I use.  

Technologies used: 

This website will be built by using these programing languages: 

HTML and CSS for creating forms and styling the webpage (since these are two of the most used front-end languages with more designs available for dynamic webpages) 

JavaScript for handling both frontend and backend 

PHP for backend and database connection  

*****************************************************************************************************************************************************************************

## Team Name: Marsia Mustafa

## Team Leader:
- **Name:** Marsia Mustafa
- **GitHub Username:** Marsia1

# Project Details

## Project Title: Website for ‘Physiotherapie Dinaj’ clinic 

## Problem Statement:
This clinic is a new business which has been operating only for the last 8 months. For the moment the only way clients can get information about the services provided by the staff is via telephone. However, the workload falls solely on one individual, responsible for attending to both new and returning clients. This arrangement occasionally leads to disarray and dissatisfaction among clients who are unable to access the information they require. 

## Solution Proposed:
The solution I came up with in accordance with the staff of the clinic, is to develop a website which contains all the needed information for new clients. This way, all clients will have a user-friendly interface which helps with all the detailed information they need to determine if the clinic has suitable services for them or not.  

## Project Scope:

I have thought of using HTML, CSS, JavaScript and PHP languages to develop my website which will be a dynamic one where each button has a specific action to cover. The delivery will be a fully functional website with interactive features and dynamic content with informational pages covering various aspects of the clinic's services, staff, facilities, and contact details. 

The main limitation of this project is the centered responsibility and the limited skill set in certain situations that may arise.   

- **Aim:** The aim of this project is to deliver a dynamic website that will help the clinic improve its relationship with the clients. 
- **Main Objectives:**
Put in practices all the knowledge gathered during this course and other ones taken during the academic year 

Deliver on time each phase and a good final product 

## Application Description:

The website will include a detailed information for all the services that this clinic offers and their respective prices, a form where the client can add their personal data so they can be contacted by the staff later, a form which will include questions about the physical side which should be completed by each client before their appointment. The patients can also book an appointment by selecting the desired date and time in accordance with the clinic plan. 

# Roles and Tasks Distribution

The project I am currently working on is a website for a physiotherapy clinic which operates in Germany. As the sole contributor of this project, my first duty was to contact this clinic and first understand their requirements and expectations. After that, I have developed a plan of how the website is going to look, what it will include and which languages I am going to use. The main responsibility is to deliver the final product on time and it to be 100% functional.  

# Deadline
Submission Deadline: 20.03.2023, 23:59 hours.
