# Overview

## Overview

### About this guide

This guide is designed to get you up and running with StifleR in a ’Proof of Concept’ or LAB environment. For full design and implementation guidelines – read the Planning and Implementation Guide.

### About StifleR

StifleR is a typical Client – Server application that uses bi-directional communication channels. The Server hosts an OWIN \(Open Web Interface for .NET\) implementation of Microsoft SignalR.

All communication is based on the Microsoft the Microsoft SignalR protocol, a web-sockets based protocol that runs over UDP, initiated first through an HTTP connection which then steps things up to web sockets. StifleR server also uses SignalR to communicate with the endpoint clients and any connected dashboards.

Understanding how SignalR works is not mandatory to use StifleR but is required if custom scripting or advanced configuration of StifleR is to be undertaken. Please refer to the 2PintSoftware Website for advanced information on the Microsoft SignalR platform.

### Pre-Flight Checklist

#### **Working P2P Infrastructure**

StifleR requires a functioning Microsoft Peer to Peer \(P2P\) infrastructure in order to fully optimize your software distributions. Typically this includes BranchCache and/or ConfigMgr Peer Cache and/or Windows 10 Delivery Optimization.

#### **StifleR Server**

A Suitable Server to act as the StifleR Server – this can be any server for the purposes of testing as the load will be very light.

#### **Client Systems**

Windows client systems are required, onto which you will install the StifleR Client software. These should represent your corporate client build \(OS revision etc\) as closely as possible.

_**Pre-requisite**_

* Windows 7 SP1 or later
* Supported are x86 or x64 versions of the operating systems
  * Professional, Enterprise or Ultimate versions
  * Newer Educational SKU is also supported

  
* Microsoft .Net 4. 6 .2 \(or higher\) must be installed on the client
* Hotfixes for Windows 7 - [https://support.microsoft.com/en-us/kb/3036149](https://support.microsoft.com/en-us/kb/3036149) _\(not required but fixes a_

    _bug within BITS that can cause it to ignore Bandwidth Policy\)_

#### **Network**

For the purposes of testing content delivery to low-bandwidth locations, we recommend that you emulate as closely as possible the WAN configuration of your production setup, sepcifically the available bandwdith. You can do this using NEWT, a VYOS Linux Router, or method of your choice.

## Features Overview

StifleR is designed to provide two main enhancements to Enterprise-wide Content Distribution.

* To greatly reduce the volume of WAN traffic transferred from content servers to remote

    client systems by using Microsoft Peer to Peer technology.

* To provide granular monitoring and control over the volume of WAN \(and LAN\) traffic, and

    provide administrators with the ability to optimize network utilization and effectively control

    bandwidth usage.

