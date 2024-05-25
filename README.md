# Patient Registration and Psychiatrists API

This repository contains the implementation of a RESTful API for registering patients and retrieving psychiatrist and patient details for a specified hospital. The backend is built using Node.js and Express.js, with MongoDB as the database.

### Major Libraries/Frameworks Used

- Express.js: Fast, unopinionated, minimalist web framework for    Node.js. Used to set up the web server and route the API endpoints.
- MongoDB: A NoSQL database used for storing and querying data.
- Mongoose: An elegant MongoDB object modeling tool for Node.js.

## Prerequisites
- Node.js
- MongoDB

### Installation

```javascript
git clone https://github.com/Ershubhamkrojha/Lattice-Task
```
### Install dependencies:
```javascript
npm Install
```
### Run the server:

```javascript
npm start
```
## API Endpoints
Register a New Patient
Endpoint: POST /api/patients

```javascript
{
  "name": "shubham kumar ojha",
  "address": "123 Main St, City, Country",
  "email": "johndoe@example.com",
  "phone": "+1234567890",
  "password": "Password1",
  "photo": "file"
}
```
### Validation:
- Name: Required
- Address: Required, minimum 10 characters
- Email: Required, valid email format
- Phone: Required, minimum 10 digits with country code
- Password: Required, 8-15 characters, must contain one uppercase, one lowercase, and one number
- Photo: Required

### Response:

- Success: 201 Created
- Failure: 400 Bad Request

### Get Psychiatrists and Patient Details for a Hospital

- Endpoint: POST /api/hospitals/:hospitalId/details

```javascript
{
  "hospialname": "Appolo Hospital"
}
```
### Response:

```javascript
{
  "hospitalName": "Apollo Hospitals",
  "totalPsychiatrists": 10,
  "totalPatients": 100,
  "psychiatrists": [
    {
      "id": "60d5f9b5fc13ae2d3b000002",
      "name": "Dr. Smith",
      "patientsCount": 10
    },
    {
      "id": "60d5f9b5fc13ae2d3b000003",
      "name": "Dr. Johnson",
      "patientsCount": 15
    }
  ]
}
```

## Database Schema
- Hospitals: _id, name
- Psychiatrists: _id, name, hospitalId
- Patients: _id, name, address, email, phone, password, photo, -  psychiatristId

# API Testing Documents

You can test the API endpoints using Postman. Access the collection


https://speeding-firefly-578920.postman.co/workspace/New-Team-Workspace~bc52b9d4-b635-414a-8aee-7be0dc07e116/collection/28763304-758369af-2373-4b0e-92d1-30bde12e3697?action=share&creator=28763304



