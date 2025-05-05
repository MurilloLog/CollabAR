# CollabAR: A Framework for Collaborative Augmented Reality Applications | I3D 2025

<div style="text-align: center;">
  <img src="./Assets/Fig_teaser.png" alt="Figure description" />
  <p>Figure description: The result of the functionality test on a simple co-located collaborative AR drawing experience over two users' mobile devices using our framework. To establish collaboration, both devices start from the same initial reference point and perform an environmental scan, as illustrated in (1). After each device locally generates spatial anchors using ARCore, the spatial drawing functionality is enabled, as shown in (2).</p>
</div>

## Overview
This repository outlines the design, development, and implementation of a framework to simplify the deployment and setup of colocated collaborative Augmented Reality (AR) experiences on mobile devices (currently supporting ARCore-compatible devices). The framework uses a centralized client-server architecture, where a single PC acts as a local server to handle data communication and synchronization across multiple connected devices. This toolkit eliminates dependencies on cloud anchor services or third-party platforms, which often impose restrictive limitations.

The project is organized into two main sections: the first covers the architecture and technical configuration of the local server (_Server folder_), describing the components and processes required to ensure its functionality; the second focuses on the client app (_App folder_), evaluation, and validation of the application, identifying issues encountered during development, analyzing potential solutions, and proposing improvements for future iterations.

## Dependencies

### Server
Refer to [SERVER.md](./Server/README.md) for setup instructions.
- **NodeJs**. Facilitates server functions (e.g., reading/sending messages).
- **Typescript**. Primary programming language for server functionalities.
- **Mongoose**. *Node.js* library for streamlined MongoDB query execution.
- **Typegoose**. Enhances Mongoose integration with Typescript syntax.
- **MongoDB**. NoSQL database system for storing objects created in the app.
- **JSON**. Object notation used for message formatting and transmission.
### Client App
Refer to [APP.md](./App/README.md) for setup instructions.
- **Unity**. Cross-platform game engine for mobile app development.
- **ARCore**. Platform used for building augmented reality experiences on Android devices.
- **.NET**. Facilitates message control between server and client.

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


