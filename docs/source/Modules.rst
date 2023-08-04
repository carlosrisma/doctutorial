========
Modules
========
.. contents:: Table of Contents
    :local:

Automotive module
==================
The automotive module is the main module of **ms-van3t** containing all the sample applications, ETSI C-ITS sub-modules, and additional auxiliary sub-modules, all listed below: 

- Facilities layer
  - Cooperative Awareness basic service (CABasicService)
  - Decentralized Environmental Notification basic service (DENBasicService)
  - Infrastructure to Vehicle Information basic service (IVIBasicService)
  - Collective Perception basic service (CPBasicService)
  - Vehicle Data Provider (VDP)
  - Local Dynamic Map (LDM)
  
- Networking and Transport layers
  - Basic Transport Protocol (BTP)
  - GeoNetworking (GeoNet) 

- Measurements 
  - Packet Reception Ratio supervisor (PRRsupervisor)

- Utilities
  - SUMO sensor

GPS-tc module
=============
The *gps-tc* module provides classes and functions to leverage offline-collected GNSS traces. This module allows realistic positioning data rather than artificial traces created with SUMO.

Vehicle Visualizer module
=========================
ms-van3t also comes with a web-based vehicle visualizer, able to display the vehicles traveling during the simulation on a map, rendered directly inside the user’s browser.
