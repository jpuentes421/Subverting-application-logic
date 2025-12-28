# Subverting-application-logic

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
6. Next, lets try to input an SQL character (') 
