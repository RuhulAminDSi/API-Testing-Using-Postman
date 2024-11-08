
# Assignment: API’s and API Testing Using Postman

## Assignment Overview
Trainees are required to create API test cases (both positive and negative) in a Collection using Postman for various operations involving Admin, System, Agent, Customer, and Merchant functionalities. The assignment includes creating a Postman collection, generating reports, and organizing everything in a GitHub repository. Please note that generating a Newman report is a BONUS task/work.

## Scenarios

### Admin Operations
- Create an agent, merchant, and two random customers as Admin.
- **Admin Credentials**:
    - Email: `admin@roadtocareer.net`
    - Password: `1234`
- Cancel Transaction.

### System Operations
- Deposit money from the SYSTEM account to the agent.
- **Amount Range**: 10 Tk to 10,000 Tk

### Agent Operations
- Deposit money to one of the customers as Agent.
- Check the agent's balance.

### Customer Operations
- Withdraw an amount from the agent (Range: 10 Tk to 10,000 Tk).
- Check customer balance.
- Send money to another customer.
- Make a payment from the second customer to the merchant.
- Check both balance and statement for the second customer.

### Merchant Operations
- Merchant checks their own balance.
- Merchant checks their own statement.

## API Documentation
- Access the transaction API URL, endpoints, header information, and demo data from the provided documentation.

## Postman Collection
- Create a Postman collection based on the test cases developed for the 10 scenarios listed above.
- Include negative test cases for each API request.

## Documentation and Reporting
Generate the following:
- **Postman Documentation**: Generate and add the link to the GitHub `README.md`.
- **Screenshots**: Include screenshots of the Newman report in the GitHub `README.md`. (BONUS)

## Automation Requirements
Automate API requests/flows, including:
- **Scripts**: Implement Pre-Request and Post-Response scripts for validations/assertions.
- **Variables**: Proper use of Collection and Environment variables. Set up at least two environments to ensure isolation.
- **Flow**: Chain APIs to create a sequential automated flow that runs successfully.

## GitHub Repository
### Task
Create a GitHub repository for the assignment.

### Deliverables
Include the following in the GitHub repository:
- Postman Collection
- API documentation
- Reports
- Screenshots

Ensure that all documentation, reports, and screenshots are correctly linked and organized in the GitHub repository. Alternatively, you may upload the Postman Collection, API documentation, reports, and screenshots to a specific folder in Google Drive.

## Submission
Ensure that all documentation, reports, and screenshots are correctly linked and organized in the GitHub repository or Google Drive.
