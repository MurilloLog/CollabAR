# A Framework for Collaborative Augmented Reality Applications | I3D 2025

<div align="center">
  <img src="./Assets/Fig_teaser.png" alt="Two users collaborating on AR drawing" width="600">
  <p><em>Figure: Real-time AR drawing synchronization between two mobile devices using our framework</em></p>
</div>

## Overview
This repository presents a framework designed to streamline the deployment and configuration of colocated collaborative augmented reality (AR) experiences for mobile devices (currently supporting ARCore-compatible devices). The solution employs a centralized client-server architecture, where a dedicated local server (PC) manages real-time data communication and synchronization across connected devices. This approach eliminates reliance on cloud anchor services or third-party platforms, which often impose restrictive limitations.

Perfect for:
- Prototyping multi-user AR experiences
- Collaborative projects
- AR education tools

## 🧩 Project Components

| Folder | Purpose | What You'll Find There |
|--------|---------|------------------------|
| `Server/` | Contains the complete architecture and technical configuration for the local server, including all necessary components and operational processes | Server code, database setup |
| `App/` | Includes the mobile application implementation that connects to and interacts with the server framework | Unity project, App setup |


## 🛠️ Setup Guide

### Before You Begin
You'll need:

✔ **Computer**: Windows/Mac/Linux with:
  - Node.js v22.12.0 ([installation guide](https://nodejs.org/en/download))
  - MongoDB 8.0.4 ([installation guide](https://www.mongodb.com/docs/manual/installation/))

✔ **Phones**: 2+ Android devices with:
  - ARCore support ([compatibility list](https://developers.google.com/ar/devices))
  - Developer mode enabled
    
✔ Refer to [SERVER.md](./Server/README.md) and [APP.md](./App/README.md) for setup instructions.

### Step 1: Get the Code
```bash
git clone https://github.com/MurilloLog/CollabAR
cd CollabAR
```

### Step 2: Launch the Server
1. **Open two terminal windows** in the `Server/` folder
2.  **In first terminal** (Database):
   ```bash
   mongod
   ```
→ Look for "waiting for connections" message.

**In second terminal** (Application):
```bash
npm install # First time only
npm start
```
This launches the server.

### Step 3: Set Up the AR App
1. Open Unity Hub
2. Add the App/ folder as a project
3. Build and install on your Android devices

## 🎨 Using the App
1. **Connect Devices**:
   - Point cameras at the same table/floor
   - Enter the server's IP address (shown when server starts)
   - Tap "Join"

2. **Start Drawing**:
  - Choose colors from the palette
  - Draw in the air - others will see your draw when you finish it!
  - Walk around - drawings stay in place

### ❓ Common Questions
**Q: Why do devices need to be close together?**
A: They share the same physical AR space - like looking at the same real painting.

**Q: Can I use iPhones?**
A: Currently Android-only (ARCore requirement), but iOS support could be added.

**Q: How many users can join?**
A: Theoretically unlimited, but performance depends on your server.

## Please kindly cite our paper as:
```
@inproceedings{10.1145/3722564.3728390,
author = {Murillo Gutierrez, Gustavo Adolfo and Jin, Rong and Ramirez Paredes, Juan Pablo Ignacio and Hernandez Belmonte, Uriel Haile},
title = {A Framework for Collaborative Augmented Reality Applications},
year = {2025},
isbn = {9798400718335},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3722564.3728390},
doi = {10.1145/3722564.3728390},
series = {I3D Companion '25}
}
```


