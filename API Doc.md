
# Dmoney API Testing Using Postman And Newman
## Project summary:
This porject shows the automation between DMoney user and Transection API using postman. And generate report using newman to show the test result at a glance. I have added the API collection run documentation, Test Cases documentation both positive and negative test case and a Bug report for this project.
## Test Scenarios:
1. Admin creates an agent and random 2 customers. 
2. Deposit some money from SYSTEM account to the agent. System account: SYSTEM (range 10 tk to 10000 tk)
3. Agent deposit to any of 1 customer
4. Check agent balance
5. Then withdraw any amount by the customer from the agent (range 10 tk to 10000 tk)
6. Then the customer checks balance
7. Then send money to the other customer
8. Then from the another customer payment to this merchant: 01686606905
9. Then the second customer will check both balance and statement
10. Then the merchant will check his own balance

## Prerequisites
``` 1. Node.js ``` <br>
``` 2. Post man ``` <br>
``` 3. Vs code ``` <br>
``` 4. Newman ``` <br>
``` 5. git ``` <br>

## Base URL
http://dmoney.roadtocareer.net


## Authentication
All requests require an `Authorization` header with a Bearer token.
Authorization: Bearer <token>

### Example Token
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZGVudGlmaWVyIjoiMDE2ODY2MDY5MDkiLCJwYXNzd29yZCI6IjEyMzQiLCJpYXQiOjE3MDEzMzIxMjMsImV4cCI6MTcwMTMzNTcyM30.VT-n02aEWKcnA879XpMh5yFQ46vRPXN80izpF05wqh0
```

## Endpoints

### 1. User Login

#### **Login with Valid Credentials**

- **Method**: `POST`
- **URL**: `/user/login`
- **Body** (JSON):
  ```json
    {
        "emailOrPhoneNumber": "01686606909",
        "password": "1234"
    }

#### **Login with Invalid Credentials**

- **Method**: `POST`
- **URL**: `/user/login`
- **Body** (JSON):
    ```json
    {
        "emailOrPhoneNumber": "01686606909",
        "password": "12345"
    }
    ```
### 2. Create User

#### **Create Agent with Valid Credentials**

- **Method**: `POST`
- **URL**: `/user/create`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```
- **Body** (JSON):
    ```json
    {
        "name": "Israel Hauck",
        "email": "Alexander_Legros65@hotmail.com",
        "password": "1234",
        "phone_number": "01913152411",
        "nid": "123456789",
        "role": "Agent"
    }
    ```
    
#### **Create Agent with Invalid Credentials**

- **Method**: `POST`
- **URL**: `/user/create`
- **Body** (JSON):
    ```json
    {
        "name": "Anika Blick",
        "email": "Willon.McGlynn@yahoo.com",
        "password": "12345",
        "phone_number": "01911531971",
        "nid": "123456789",
        "role": "Agent"
    }
    ```
### 3. Create Customer

#### **Create Customer 1**

- **Method**: `POST`
- **URL**: `/user/create`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```
- **Body** (JSON):
    ```json
    {
        "name": "Mrs. Rochelle Howell",
        "email": "Arlie.Purdy@hotmail.com",
        "password": "1234",
        "phone_number": "01913638099",
        "nid": "123456789",
        "role": "Customer"
    }
    ```

#### **Create Customer 2**

- **Method**: `POST`
- **URL**: `/user/create`
- **Body** (JSON):
    ```json
    {
        "name": "Nathan Williamson",
        "email": "Osborne84@gmail.com",
        "password": "1234",
        "phone_number": "01913638099",
        "nid": "123456789",
        "role": "Customer"
    }
    ```

### 4. Transactions

#### **Deposit Money**

- **Method**: `POST`
- **URL**: `/transaction/deposit`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```
- **Body** (JSON):
    ```json
    {
        "from_account": "SYSTEM",
        "to_account": "01913152411",
        "amount": 5000
    }
    ```

#### **Withdraw Money**

- **Method**: `POST`
- **URL**: `/transaction/withdraw`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```
- **Body** (JSON):
    ```json
    {
        "from_account": "01914032049",
        "to_account": "01913152411",
        "amount": 50
    }
    ```

### 5. Balance Check

#### **Check Agent Balance**

- **Method**: `GET`
- **URL**: `/transaction/balance/<agent_number>`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```

### 6. Payment

#### **Merchant Payment**

- **Method**: `POST`
- **URL**: `/transaction/payment`
- **Headers**:
    ```
    Authorization: Bearer <token>
    X-AUTH-SECRET-KEY: ROADTOSDET
    ```
- **Body** (JSON):
    ```json
    {
        "from_account": "01913638099",
        "to_account": "01686606905",
        "amount": 11
    }
    ```

### Error Handling

- Ensure to validate inputs and handle errors gracefully. Common errors include invalid credentials, insufficient funds, and non-existing accounts.

---

This documentation provides a structured overview of the Dmoney Transaction API.
