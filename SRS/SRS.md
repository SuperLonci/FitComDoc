Product title:
## FitCom

Developer team:
### Daniel Gombar, Ian Helmrich, Cem Yilmaz

Last update:
### 18th October 2020


# 1 Introduction
## 1.1 Purpose of this Document
This document is the System and Software Requirements Specification (SRS) for the development of the "FitCom" service. It is supposed represent the requirements for the product "FitCom" agreed between the customer and the development team.


## 1.2 Scope of the Product
The Fitcom service is intended to enable members of authorized fitness centers to create, display and share training plans. In addition, they should be able to document their own training progress. Personal trainers of the fitness center should also be able to distribute training plans to their members.


## 1.3 Overview of the Document / Table of Contents
- [1 Introduction](#1-introduction)
    - [1.1 Purpose of this Document](#11-purpose-of-this-document)
    - [1.2 Scope of the Product](#12-scope-of-the-product)
    - [1.3 Overview of the Document / Table of Contents](#13-overview-of-the-document-/-dable-of-contents)

- [2 Overall Description](#2-overall-description)
    - [2.1 Product Information](#21-product-information)
    - [2.2 User Properties](#22-user-properties)
    - [2.3 Assumptions and Dependencies](#23-assumptions-and-dependencies)
    - [2.4 Distribution of Requirements](#24-distribution-of-requirements)

- [3 Specific Requirements](#3-specific-requirements)
    - [3.1 Functional Requirements](#31-functional-requirements)
    - [3.2 Non-Functional Requirements](#32-non-functional-requirements)
    - [3.3 Architecture Details](#33-architecture-details)
    - [3.4 Design Constraints](#34-design-constraints)


# 2 Overall Description
## 2.1 Product Information
For the "FitCom" service administrators of a fitness center, it should be possible to grant and withdraw their employees the rights to create and distribute training plans to members of the fitness center. For those a mobile app should be available in which training plans created by the persolnal trainer can be displayed, but can also be created and edited themselves. Within this app, the members of the fitness center should also be able to document their training progress.


## 2.2 User Properties
The members of the fitness center are intended as the main user group, but its management and its trainers will also have to use the system.


## 2.3 Assumptions and Dependencies
The mobile app should be available for Android and iOS devices. A web interface should be available for the interaction between the employees of the fitness center and the service. 


## 2.4 Distribution of Requirements
For future versions of the service, a challenge system is to be established in which the members of the fitness center can voluntarily share their successes.


# 3 Specific Requirements
## 3.1 Functional Requirements
The Subsystems are:

- News Board:
The news board is the essential part of the apps user interface. Trainers can post challenges there and shared sets by other members can be viewed on this page. Furthermore it is possible to interact with those shared sets and post reactions. 

- Account System:
Upon first start up of the app the user needs to scan the QR Code of the Gym to create a User Account. The users training plans are stored on the server and the trainer can change improve the users plans via this account. User data must be stored alongside the training data.

- User Highscores:
Users can score Highscores by e.g lifting the most weight. These can be accessed through a leaderboard.

- Connecting People:
An important aspect is connection the members. This will be reached by making it possible to interact with highscores or shared trainings.
Furthermore this should be reached by making it possible to acceppt challenges by the trainer which will be send by push notifications. The results will be displayed in a leaderboard.

- Storing Data:
User data for accounts needs to be stored. Also the training progress and history will be stored. The data storage will form the foundation for the visualization and the account system.

- Training Plans:
There are basic training plans provided by standard.
Furthermore the trainer can make training plans for you which are then showed in your app.

- Tracking trainings:
User can track their trainings (wheights and repititions) and save them in the app. Their history is also saved so that they can see their progress.

### 3.1.1
[Overview Use Case Diagrams](../uml_diagrams/overview.md)

#### 3.1.1.1 Generating a QR-Code for each gym
Because each individual gym has its own community it has to be the entry point for a new account creation. By scanning a QR-Code, that is displayed in the gym, users can start the registration process. We need to be able to provide QR-Codes for those gyms.

#### 3.1.1.2 Scanning the gym QR-Code to request an account
Inside the mobile App we need the ability to detect QR-Codes with the device's camera and use them to send requests to the administrators.
[Account Creation UCD](../uml_diagrams/create_account_uml.svg).

#### 3.1.1.3 Confirming account requests
In the web application the administrators have to confirm the incoming requests of the fitness center members.

### 3.1.2 Entering fitness plans for specific users
If the fitness center member desires, he can ..

### 3.1.3 Displaying fitness plans for the user
TBD
### 3.1.4 Progress tracking
[Start a workout](../uml_diagrams/start_workout_uml.svg).

### 3.1.5 Hall of fame
TBD
### 3.1.6 Multi gym support
TBD

## 3.2 Non-Functional Requirements
IT security: Since part of the stored data is personal, the database should be secured against unauthorized access. 

## 3.3 Architecture Details
<img src="../uml_diagrams/uml_diagram.svg">

## 3.4 Design Constraints
Both the web interface for the employees of the fitness center and the mobile app should comply with Apple's human interface guidelines.