---
layout: home
permalink: index.html

# Please update this with your repository name and project title
repository-name: e18-3yp-smart-glove
title: Smart Glove

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# Smart Glove

---


<!-- Image (photo/drawing of the final hardware) should be here -->

<!-- This is a sample image, to show how to add images to your page. To learn more options, please refer [this](https://projects.ce.pdn.ac.lk/docs/faq/how-to-add-an-image/) -->

<!-- ![Sample Image](./images/sample.png) -->

#### Table of Contents
1. [Introduction](#introduction)
2. [Solution Architecture](#solution-architecture )
3. [Hardware Design](#hardware-design)
4. [Software Design](#software-design)
5. [System Requirements](#system-requirements)
6. [Final Result](#final-result)
7. [Testing Plan](#testing)
8. [Detailed budget](#detailed-budget)
9. [Demonstration](#demonstartion)
10. [Timeline](#timeline)
11. [Project Team](#team)
12. [Links](#links)

# Introduction
---

<video src="./videos/SmartGloveIntro.mp4" controls="controls" style="max-width: 730px;">
</video>


Currently, around 10% of the world population or roughly 650 million people live with a disability. Among them there are around 15% - 20%  deaf and dumb people. Most of them use sign language to communicate with the outside world. But certain percentage can understand this sign language. So, to overcome this problem we introduce a new product called smart glove which can sensor the movements of the hand. Those sensor values are converted into a text and a speech which can be used  by a third party to understand those sign language movements. Those who do not know how to use sign language can use our application to convert their audios to sign language.
Also this makes it easier for the average individual to comprehend what he is saying and respond appropriately. The ability to operate home appliances is a feature of this smart gloves that enables people with physical disabilities to live independently. The primary goal of the product is to create a dependable, user-friendly, lightweight smart hand glove system that can reduce barriers for persons with disabilities so they may participate in races.

### Why Sign Language ?

Communication is an important tool for every human being. Sign language is visual language extemely important communication native for many hard of hearing people. It also used by any people who want to communicate with such people and , also who can hear but can't talk. So sign languages bridge the gap between the disabled and normal person. 

<p align="center">
<img src="https://user-images.githubusercontent.com/73567971/204220493-36158f5c-c576-45d4-919a-450c1470727d.jpg" width="600" height="300"></p>

### Why Smart Glove ?

Those people solely communicate with others through their hands and facial gestures. They typically find it difficult to communicate with others, therefore we focused this project to help them. The major goal is to help those people  by breaking down communication barriers so they are not restricted in a limited social circle and 
may express their feelings whenever they wish. Additionally, it would be beneficial in areas of health and education related to them. In our scope we focuse on hand sign language. Among them, American Sign Language (ASL) is one of the most widely used one. 

### What is Smart Glove ?

With the use of a smart glove, we can solve the issues that the disabled encounter, helps to understand what mute person is trying to say and reply accordingly. 


# Solution Architecture
---

### Our Solution

Smart Glove

  - Convert sign language to text
  - Detect signs accurately

  
Mobile app
  
  - Communicate between any of Glove users, Communicative users
  - Provide long distance communication
    (By translating between text/voice messages & sign language)

### System Design
<p align="center">
<img src="./images/ProposedSystem.png" width="600" height="300"></p>


### Data flow and Storage

### Embedded System
<p align="center">
<img src="./images/EmbeddedSystem.png" width="600" height="300"></p>


### Circuit Diagram
This is the overall circuit diagram for the device. It has Node MCU microcontoller, 16 channel analog multiplexer, acclerometer and flex sensors. Since Node MCU microcontroller has a WiFi module, rather than using arduino board the selection was done to choose this microcontroller. So, the below diagram shows how flex sensor inputs and accelerometer inputs are taken by this microcontroller. The 16 channel analog multiplexer is used because the Node MCU microcontroller has only one analog input. So, n=it is needed to increase this to 8 for 5 flex sensors and 3 inputs of X,Y,Z from accelerometer. By considering the further improvements the decision was taken as 16 channel MUX rather than 8 channel MUX.
<p align="center">
<img src="./images/circuit2.png" width="600" height="300"></p>

### Overall Control Flow
<p align="center">
<img src="https://user-images.githubusercontent.com/73567971/204489307-aa4a20ae-41c1-4c4e-9280-9ef95648460b.png" width="600" height="300"></p>



### Device Algorithm
<p align="center">
<img src="https://user-images.githubusercontent.com/73567971/204488129-b9f57153-b902-4368-bc1f-f13935ae5482.png" width="600" height="300"></p>


### Features of the design
- Can act as both mobile & web applications
- Chat with glove user using an unique model number
- Communicate using voice/ text as prefer
- Keep the privacy of chats using reconnect method
- Translate texts to sign images for glove user


### Key features of the product

#### Scalability
- Implemented in AWS
- Load balancing

#### Efficiency
- Make fast API calls GET, POST, PUT through REST API
- Data validation done from front end

#### Security aspects
- Encrypt the password
- Limit access to the database by whitelisting IP addresses
- Only one user can communicate with a glove at a time


<video src="./videos/UIDesigns.mp4" controls="controls" style="max-width: 730px;">
</video>



### Back End Control Flow
<p align="center">
<img src="./images/backendControlFlow.png" width="600" height="300"></p>



# Hardware Design
---

## Implementation

## Components

### Controller platform
- Node MCU Microcontroller
    <p align="left">
    <img src="https://user-images.githubusercontent.com/73390233/204560770-fb5a943c-e37d-426b-a864-07e7eb4ab475.png" width="300" height="200"></p>
  

### Sensors
- 3 - Axis Accelerometer Module (G Sensor)

  <p align="left">
  <img src="https://user-images.githubusercontent.com/73390233/204561322-f7166156-8d7c-4c8c-a8dd-4b57358f7808.png" width="300" height="200"></p>
- Flex sensors

  <p align="left">
  <img src="https://user-images.githubusercontent.com/73390233/204561752-b55cec51-8b6c-462c-8591-5818ce815741.png" width="300" height="200"></p>

### Power supply
- Rechargeable battery
  <p align="left">
  <img src="https://user-images.githubusercontent.com/73390233/204559075-fbb33fee-4550-47d1-a420-eb04f0b5ecd9.png" width="200" height="150"></p>
- Switch button (power ON)
  <p align="left">
  <img src="https://user-images.githubusercontent.com/73390233/204558521-5b1e84bc-e60b-4b84-8433-fbe77d9b67c2.png" width="200" height="150"></p>


## How Flex Sensor Works
It is used a resistors to get the flex sensor readings , according to the bending the output valu may changes 
When the bending is 0, the circuit diagram looks like this
<p align="left">
<img src="./images/flex sensor1.png" width="300" height="150"></p>
This is an example of flex sensor measurement when there is some bending in the sensor(116 degrees)
<p align="left">
<img src="./images/flex sensor2.png" width="300" height="150"></p>
<p align="left">
<img src="./images/flex snesor3.png" width="200" height="200"></p>

## How Accelerometer Works

The below circuit diagram shows how accelerometer readings can be taken in 3D space. It outputs the X, Y, Z direction reading to the LCD display for the visualization. This is done for the testing of the accelerometer
<p align="left">
<img src="./images/accelerometer.png" width="600" height="300"></p>

## Prototype Design

<img src="./images/prototype.jpg" width="400" height="500"></p>

### Hardware Testing
- Flex Sensor Testing
    Flex sensors are tested by connecting them to a separate circuit like above and check the functionality of those sensors
- Accelerometer Testing
    Accelerometer is tested by connecting it to a separate circuit like above and check the output via a LCD display
- Overall Hardware Product Testing
    Check the overall functionality of the device by sending messages to the mobile application. Examine the latency and the accuracy

#### Implementation


# Software Design
---

## Implementation

Implentations UI designs for the mobile app

- Get Started interface


<p align="left">
<img src="./images/getstarted.png" width="250" height="450"></p>


- New mobile app user register interface


<p align="left">
<img src="./images/register.png" width="250" height="450"></p>


- Already registered user sign in


<p align="left">
<img src="./images/signin.png" width="250" height="450"></p>


- Newly users recent chat interface


<p align="left">
<img src="./images/defaultchat.png" width="250" height="450"></p>


- Add a chat with a new user 


<p align="left">
<img src="./images/newchat.png" width="250" height="450"></p>

### Front End Technology

<p align="left">
<img src="./images/Flutter.png" width="300" height="150"></p>

Why?
  - onecode base for all platforms
  - hot reload - make changes in real time
  - rich libraries - quick loading, smooth app experience


### Back End Technologies

<p align="left">
<img src="./images/tech.png" width="500" height="250"></p>

<p align="left">
<img src="./images/MongoDB.png" width="300" height="150"></p>

Why?
  - Full cloud based developer data platform
  - Flexible document schemas
  - High performance

<p align="left">
<img src="./images/aws.png" width="300" height="150"></p>

Why?
  - Easily scalable (up or down)
  - Pay for what you use
  - Have complete control
  - Highly secure
  - Can access assets from anywhere in the world


### Network Technologies

<p align="center">
<img src="./images/Network.png" width="600" height="300"></p>

### Software Testing

#### Front End Testing (Flutter test library)

Unit tests 
  
  - Check user sign up and sign in
      - Only eligible users can access
      - Check user credentials 

Integration tests

  - Verify app’s performance


#### Back End Testing  (Postman)

  - Check functionality of every API endpoint
      - Correct response data
      - Correct Status code

<p align="left">
<img src="./images/postman.png" width="300" height="150"></p>

# System Requirements
---

Security

  - Encrypt data (Hash Coding)
  - Unique model number for each glove

Performance

  - Accuracy of the conversions
      - Sign language to text
      - Text / Voice to images
  - Minimum Latency

Power

  - Rechargeable batteries to power up
  - 3.3V supply voltage

# Final Result
---
<p align="left">
<img src="./images/testBYE.png" width="500" height="250"></p>

<p align="right">
<img src="./images/testResult.png" width="500" height="250"></p>

<video src="./videos/UIDesigns.mp4" controls="controls" style="max-width: 730px;">
</video>

# Testing Plan
---
## Software Testing

| Test                      | Method                       | Outcome                                |
| --------------------------|:----------------------------:|:--------------------------------------:|
| Authority Testing         | Flutter test library         | Prevent Unauthorized Access            | 
| API Testing               | POSTMAN                      | Accuracy of the requests               |
| Unit Testing              | Flutter test library         | Performance of each units in the App   |  
| Integration Testing       | Flutter test library         | Overall Performance of the App         |  


## Hardware Testing

| Test                      | Method                       | Outcome                                                       |
| --------------------------|:----------------------------:|:-------------------------------------------------------------:|
| Calibration Testing       | Manual calibration           | Ensure that all components are working fine                   | 
| Functionality Testing     | Manual Testing               | Accurately detect the sign each hardware checked separately   |
| Compatibility Testing     | Manual Testing               | Ensure that device is compatible with the system              |  
| Performance Testing       | Manual Testing               | Detect sign with minimum latency                              |  


### NodeMCU & Flex Sensor 

Circuit :

Output :

# Detailed budget
---

| Item                      | Quantity  | Unit Cost (LKR)  | Total Cost (LKR)  |
| --------------------------|:---------:|:----------------:|------------------:|
| Node MCU microcontroller  |  1        | 2100             |  2100             |
| 16-Channel Analog Mux     |  1        |  540             |   540             |
| 3-Axis Accelerometer      |  1        |  800             |   800             |
| Flex Sensors              |  5        | 5000             |  2500             |
| Glove                     |  1        |  500             |   500             |
| Switch Button             |  1        |  120             |   120             |
| Rechargeable Battery      |  1        |  800             |   800             |
| Node MCU microcontroller  | 10        |   80             |   800             |
| Total Cost                |           |                  | 33660             |

# Demonstartion Video
---

https://youtu.be/ddnNoUjW6rw

# Timeline
---

What was achieved, future developments, commercialization plans

# Project Team
---

#### Project Supervisors

-  Dr. Isuru Nawinne, [isurunawinne@eng.pdn.ac.lk](mailto:name@email.com)
-  Dr. Mahanama Wickramasinghe, [mahanamaw@eng.pdn.ac.lk](mailto:name@email.com)

#### Project Developers

-  E/18/010, Avishka Abeywickrama, [e18010@eng.pdn.ac.lk](mailto:name@email.com)
-  E/18/156, Thakshila Jayathilake, [e18156@eng.pdn.ac.lk](mailto:name@email.com)
-  E/18/329, Nirasha Sewwandi, [e18329@eng.pdn.ac.lk](mailto:name@email.com)


# Links
---

- [Project Repository](https://github.com/cepdnaclk/{{ page.repository-name }}){:target="_blank"}
- [Project Page](https://cepdnaclk.github.io/{{ page.repository-name}}){:target="_blank"}
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # (Please refer this to learn more about Markdown syntax)
[//]: # (https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
