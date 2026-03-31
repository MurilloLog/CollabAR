# Server Setup Guide
This document provides detailed instructions for configuring the local server that powers the collaborative AR experience.

## Server Directory Structure
Before proceeding, ensure you are working within the correct *Server* directory:
```
CollabAR/
└── App/
├── Assets/
├── *Server/*
|    ├── src/
|    │   └── lib/
|    │   ├── MatchMaking/
|    │   ├── models/
|    │   ├── Utils/
|    │   ├── views/
|    │   ├── database.ts
|    │   ├── index.ts
|    |   └── Server.ts        # Main server configuration file
|    ├── package.json         # Node.js dependencies
|    ├── package-lock.json
|    ├── tsconfig.json
|    ├── .gitignore
|    └── README.md
└── README.md
```
All commands in this guide must be executed from the ```CollabAR/Server/``` directory unless otherwise specified.

## Step 1: Verify PATH Configuration
After installation, verify that Node.js, npm, and MongoDB are properly added to your system PATH:

1. Open **Command Prompt**
2. Run the following commands:

```bash
node --version
npm --version
mongod --version
```

**Expected output:** Each command should return a version number (e.g., v24.14.1, v11.11.0, v8.2.6).

**If any command fails** ("not recognized as an internal or external command"):

- The software was not added to your PATH during installation
- You will need to add it manually or reinstall with the *Add to PATH* option selected
- Refer to the installation guides for PATH configuration instructions

## Step 2: Configure MongoDB Data Directory
MongoDB requires a dedicated directory to store database files:

1. By default, MongoDB looks for data at C:/data/db

2. From a Command Prompt **create this directory manually:**
```bash
mkdir C:\data\db
```

3. If you prefer a different location, you can specify it when starting MongoDB:
```bash
mongod --dbpath "D:\a\custom\path"
```

⚠️ **Important:** MongoDB will fail to start if this directory does not exist. Create it before proceeding.

## Step 3: Install Node.js Dependencies
Navigate to the server directory and install the required packages:
```bash
cd CollabAR/Server
npm install
```
**What this does:**
- Reads the ```package.json``` file
- Downloads and installs all required dependencies
- Creates the ```node_modules/``` folder

**First-time only:** This command needs to be executed only once. You do not need to run it again unless:
- You pull a new version from the repository with updated dependencies
- You manually modify package.json

**If you see warnings about outdated packages:**
- npm may suggest updating specific packages
- You can safely update them if no breaking changes occur
- If issues persist, feel free to open a GitHub issue to request dependency updates

## Step 4: Start MongoDB
1. Open a **Command Prompt** window
2. Start the MongoDB service:
```bash
mongod
```
3. Keep this terminal open - closing it will terminate the database service

**Successful startup:** You should see a log message: ```"ctx":"initandlisten","msg":"mongod startup complete"```

**Optional:** Install [MongoDB Compass](https://www.mongodb.com/try/download/compass) for a graphical interface to manage your databases.

## Step 5: Start the Node.js Server
1. Open a second **Command Prompt** window
2. Navigate to the server directory:
```bash
cd CollabAR/Server
```
3. Start the server:
```bash
npm start
```
**Successful startup:** You should see the log message: ```"Waiting for connections..."```

⚠️ **Keep both terminals** open while using the application:
- Terminal 1: MongoDB service (```mongod```)
- Terminal 2: Node.js server (```npm start```)

To stop the servers safely: Press ```Ctrl + C``` in each terminal.

## Configuration
To modify server behavior, edit ```src/Server.ts```:
| Parameter	| Description |
|-----------|-------------|
| PORT | Connection port (default: 8080) |
| USERS_PER_ROOM | Minimum clients required to start experience |
| databaseConfig	| MongoDB connection settings |

After making changes, restart the server:
- Press ```Ctrl + C``` to stop
- Run ```npm start``` again
