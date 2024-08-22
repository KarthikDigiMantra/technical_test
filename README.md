## Task - Submit loan application
Create the functionality for a broker to submit a new loan application.

  1. Show a modal after clicking the "Submit application" button, and allow the broker to enter the following information:
   
        - applicant_name
        - applicant_email
        - applicant_mobile_phone_number
        - applicant_address
        - annual_income_before_tax
        - incoming_address
        - incoming_deposit
        - incoming_price
        - incoming_stamp_duty
        - loan_amount
        - loan_duration
        - monthly_expenses
        - outgoing_address
        - outgoing_mortgage
        - outgoing_valuation
        - savings_contribution
        - 
### I have made the form submitted to backend with all form data by replacing method calling from form tag to submit onclick event
<img width="933" alt="image" src="https://github.com/user-attachments/assets/fc73976c-f9b7-47e0-ab6b-393af8a47c09">

  2. Add a backend endpoint to receive the application submission
### There was create application end point (brokers/applications/create-applications?) available, I have reused it to submit the form application . I have rewritten to make it more applicable for the tasks given.
<img width="593" alt="image" src="https://github.com/user-attachments/assets/b9d8c665-02d9-4136-bf9e-1dc8e6023e04">
     
  4. Query all existing applications and get the average `loan_amount`
### There was method to query average loan of all application which i have leveraged further for below tasks 
<img width="669" alt="image" src="https://github.com/user-attachments/assets/facf3948-2571-44f1-96fa-48debea77534">

     
  6. Save the new application to the `applications` table
### I have saved all of the form fields onto respective application table on postgres db. There was issue for strring columns which i thought it's was isolated issue on my side, however i have resolved them as well by having expliciate mapping of form body to application DTO 
<img width="674" alt="image" src="https://github.com/user-attachments/assets/6291e210-806f-4502-8f02-e97d3a9d6d0d">

  8. Return if new loan's loan_amount is above or below the average
### I have checked the current application loan amount is greater than average and send the boolean flag accordingly as below 
<img width="361" alt="image" src="https://github.com/user-attachments/assets/393629da-2780-4188-89ca-df17242df3ee">
<img width="656" alt="image" src="https://github.com/user-attachments/assets/87b6f5be-9c0c-4682-91ab-ab77a45b7112">








<!-- omit in toc -->
# Bridgit competency test

Welcome to the Bridgit technical test. There are three tasks of increasing complexity. After you have set up the software complete as many tasks as you can in the allotted timeframe.

| Project  | Description                                |
|----------|--------------------------------------------|
| Database | PostgreSQL managed by Sequelize Migrations |
| Backend  | NodeJS/Typescript with NestJS framework    |
| Frontend | VueJS/Typescript                           |

<!-- omit in toc -->
### Table of contents

- [Setting up](#setting-up)
- [Task - Submit loan application](#task---submit-loan-application)

![Broker portal](broker-portal.png "Broker portal")

## Setting up

Prerequisites: 

- NodeJS 16
- Docker

Setting up the database on `postgres://user:password@localhost:5436/technical_test`:

```bash
# start postgresql server using Docker's "Compose"
$ docker-compose up -d 
# create and populate the database using Sequelize
$ cd database
$ cp .env.localdev .env
$ npm install
$ npm run build
$ npm run migrate
$ npm run seed:all
```

Setting up the backend on `http://localhost:7100` with Swagger on `http://localhost:7100/swagger`:

```bash
$ cd backend
$ cp .env.localdev .env
$ npm install
$ npm run start:dev
```

Setting up the frontend on `http://localhost:7200`:

```bash
$ cd frontend
$ cp .env.localdev .env
$ npm install 
$ npm run start:dev
```

Log in to the frontend as broker 1. You can find the login information in the database seeder script.

## Task - Submit loan application
Create the functionality for a broker to submit a new loan application.

  1. Show a modal after clicking the "Submit application" button, and allow the broker to enter the following information:
   
        - applicant_name
        - applicant_email
        - applicant_mobile_phone_number
        - applicant_address
        - annual_income_before_tax
        - incoming_address
        - incoming_deposit
        - incoming_price
        - incoming_stamp_duty
        - loan_amount
        - loan_duration
        - monthly_expenses
        - outgoing_address
        - outgoing_mortgage
        - outgoing_valuation
        - savings_contribution
  
  2. Add a backend endpoint to receive the application submission
  3. Query all existing applications and get the average `loan_amount`
  4. Save the new application to the `applications` table
  5. Return if new loan's loan_amount is above or below the average

Commit your code to your personal git and share the link with us.
