![Arkham Logo](./Arkham-ui/src/assets/arkham.png)

> A graph visualization tool built with the React.js library

## Table of Contents

[1. Overview](#overview)

[2. Dependencies](#dependencies)

[3. Installation](#installation)

[4. Usage](#usage)

[5. Security](#security)

## 📝 Overview
Arkham is a graph visualization tool built within the React.js library. This application allows for extensive and efficient graph manipulation and visualization. Data can be created, edited, and deleted from within the application, with all changes being saved to a database. This tool can be used to portray any graph-type data set, whether it be personnel, device networks, or equipment matrix.

### Features
  - Visualize graph data
  - Manipulate the graph data (create, edit, and delete nodes and links)
  - Import CSV data to the graph
  - Export your workspace (with the changes you made) into a CSV file
  - All data is saved into a database for future usage
  - Secure account registration and login

## 📦 Dependencies

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
- multer

## 🏗️ Development Installation

For development purposes, you may clone the repo to your development environment.
- Prefered OS: Debian-based Linux 5.x
- The primary repo is located at: https://github.com/Artemis-Holdings/Arkham-Dev
  - NOTE: Please request access to Artims Org to clone the repo.

- Clone the repo to your development environment.
  - `$ git clone --recurse-submodules -j8 https://github.com/Artemis-Holdings/Arkham-Dev`

- run `docker-compose up` within the Arkham-Dev dir. This will build dependencies (2x postgres DBs, 1x Keycloak container) for development.

- Go to each of the sub-directories and run `npm install` to install the dependencies then start.

  - `npm install` in both the UI and API repos
  - `npm start` to start the API server
  - `npm start` to start the React UI server

-  Ensure the .env variables matches the DB name.
- Through Knex, run the latest migration `npx knex migrate:latest`
- Setup .env variables
    - CONNECTION_STRING: connects to PostgreSQL Docker container also running on local computer
        - Format: `postgres://USER_NAME:PASSWORD@localhost/DB_NAME`
- 
- Go to http://localhost:3000 to access the UI server
- Go to http://localhost:6969 to access the API server
- Go to http://localhost:8080 to access the KeyCloak server

View your development build at `http://localhost:3000/`

## Usage
Live build is currently located at [http://arkham-gov.eastus2.cloudapp.azure.com:3000](http://arkham-gov.eastus2.cloudapp.azure.com:3000)

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

### CSV Formatting
For the current build of this application, CSV files must follow a specific formatting in order to ensure a proper import. Files must contain the following headers:

 - [*EMPTY COLUMN*, id, name, color, symbolType, notes, size, source, target]

The first 6 columns are node data, with the last two (source and target) being a link for each one of these nodes. Also, ensure the CSV files are comma delimited.
