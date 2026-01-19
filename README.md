# Subverting-application-logic

Author: Jessica Puentes


Published: January 19, 2026

## Objective

 Completing a lab that contains a SQL injection within the login function. Will have to exploit the vulnerability by performing a SQL injection attack that logs in to the application as the <kbd>administrator</kbd> user.
I completed this lab using Burpsuite WebSecurity Academy. 
 

### Tools Used

- Burpsuite WebSecurity Academy


## Steps

1. Log into the Burpsuite WebSecurity Academy and select SQL injection labs. This lab is actually step 8 out of 51, so chose the lab 'Subverting application logic'
2. Click on **Access the Lab**
3. This will direct you to the We Like To Shop webpage, click on **My account** to access in the login page
4. First, let's try admin for username and admin for the password, default username and password credentials.
5. We receive the non-verbal generic error message: **Invalid username or password** non-verbal is great to use because it does not contain information regarding if the username or the password was incorrect. For example, if the error indicated that the username was wrong, this gives an attacker the opportunity to enumerate usernames on the system, a vulnerability on its own.
   <img width="1306" height="747" alt="admin admin " src="https://github.com/user-attachments/assets/fb4b4276-080c-4285-a1b8-ec20e104e65a" />
6. Next, lets try to input an SQL character (') for the username and password we will input random characters.
7. Now we have received an internal server error which indicates that something occured on the backend that broke the application. This is however a good indication that the application is vulnerable to an SQL injection.
   <img width="1306" height="747" alt="internal server error" src="https://github.com/user-attachments/assets/30fd78a4-50b8-409e-b712-15102142ce85" />

This is how the query may have looked from the backend: <kbd>SELECT firstname FROM users where username= ''' and password= 'sodfhsldiufliasdufsudf'</kbd>
The internal server error may have occured because the quote (') character interferred with the query-it closed the single quote and now left with a single quote on its own, and the rest of the query strong threw a syntax error resulting in an internal server error at the application level. 
8. Now let's login as <kbd>administrator</kbd> and inject an SQL injection that will have the system ignore the password field. The backend query would resemble this: <kbd>SELECT firstname FROM users where username='administrator'--' and password=lisdjflskjdf</kbd> Again, we can input the password as anything since we are directing the query to ignore the password. 

<img width="375" height="265" alt="Screenshot from 2025-12-28 18-08-02" src="https://github.com/user-attachments/assets/3da1c4f0-9c45-4c50-8aed-d89d5ae84aaa" />

9. We have succesfully logged in as <kdb>administrator</kdb> and have bypassed the password. 

<img width="1262" height="607" alt="Screenshot from 2025-12-28 18-09-45" src="https://github.com/user-attachments/assets/3759c67e-5ab6-48ed-9bda-f6bac9a08ef8" />


