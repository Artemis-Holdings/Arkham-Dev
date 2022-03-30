![Arkham Logo](./Arkham-ui/src/assets/arkham.png)

> A graph visualization tool built with the React.js library

## Table of Contents

[1. Overview](#overview)

[2. Dependencies](#dependencies)

[3. Installation](#installation)

[4. Usage](#usage)

[5. Security](#security)

## Overview
Dead drop provides users with secure and anonymous file sharing. All messages and Binary Large Objects (BLOBS) are encrypted. There are no user accounts; instead, users create dead-drops using a hash & pass combo.

### Features
  - Compleately anonymous file sharing. No users. No email.
  - Dead Drops with unmodified passwords are deleted after a certian ammount of time
  - Encrypted file & messaging storage
  - Modify dead-drops anonymously

## Dependencies

Front End (UI):
- Docker
- Dotenv
- Azure BLOB
- React
- pg
- Material UI (MUI)
- Keycloak
- react-d3-graph

Back End (API):
- Morgan (API request details)
- Nodemon
- Jest
- Testing-Library
- Express
- Knex
- express-fileupload
- fs

## Dev Installation
For development purposes, you may clone the repo to your local computer. After cloning both the UI and API repos run the following commands:
- `npm install` in both the UI and API repos
- `npm start` to start the API server
- `npm start` to start the React UI server
- Create PostgreSQL Docker container. Ensure the .env variables matches the DB name.
- Through Knex, run the latest migration `npx knex migrate:latest`
- Setup .env variables
    - CONNECTION_STRING: connects to PostgreSQL Docker container also running on local computer
        - Format: `postgres://USER_NAME:PASSWORD@localhost/DB_NAME`
- 
- Go to http://localhost:3000 to access the UI server
- Go to http://localhost:6969 to access the API server
- Go to http://localhost:8080 to access the KeyCloak server

<br>
<br>

## Usage
Live build is currently located at [http://arkhamdevops.eastus.cloudapp.azure.com:3000/](http://arkhamdevops.eastus.cloudapp.azure.com:3000/)

### 1. Login
1. Utilize the keycloak login services to register an account
2. Login with your newly created account

### 2. Import Data
1. From the main page of the application, open the sidebar with the menu button in the top left corner
2. Upload your desired .CSV file (see below for info on formatting .CSV files) and hit the `Upload` button

### 3. Manipulate Data
1. Your data will now appear on the main canvas
2. You can click and drag nodes to position your data how you desire
3. Left-click on a node to open the node menu where you can create links, delete links, edit node data, and view node information
4. You are also able to add nodes to the dataset
5. All changes made to the dataset will be saved to the application's database for futher viewing

### Example file upload:

![Example File Upload GIF](./message.gif)


### Example data manipulation:

![Example Data Manipulation](./file.gif)
