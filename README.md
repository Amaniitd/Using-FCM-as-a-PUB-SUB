# Using FCM as a PUB-SUB

## Overview

## Overview

This project demonstrates the use of Firebase Cloud Messaging (FCM) for server-client communication in a publish-subscribe model. In this system, the server acts as the publisher, sending out messages to the system, while clients function as subscribers, actively listening for these notifications. Upon receiving a message, a subscriber can choose to act on it, enabling dynamic and responsive communication. 

The project encompasses a Spring Boot backend, which handles the server-side functionalities, and a frontend component (in React) to manage the client-side interactions. The backend is responsible for subscribing clients to specific topics, sending notifications. Meanwhile, the frontend focuses on handling incoming notifications and providing mechanisms for clients to unsubscribe from topics if desired.


Backend: https://github.com/Amaniitd/FCM_backend

Frontend: https://github.com/Amaniitd/FCM_web_app

### Features

- Send notifications from the server to subscribed clients.
- Subscribe/unsubscribe clients to specific topics.
- Handle notification messages on the client side.

## Getting Started

### Prerequisites

- Java
- Node.js
- npm or yarn
- Firebase account

### Backend
- Clone this repo (written in Java Springboot): https://github.com/Amaniitd/FCM_backend

### Frontend
- Clone this repo (written in React): https://github.com/Amaniitd/FCM_web_app

## Usage

### Backend

#### Subscribe to Topic:
To subscribe a client to a topic, send a POST request to `/api/fcm/subscribe` with the client's FCM token and the topic name. The server will then use Firebase Cloud Messaging to subscribe the token to the specified topic.

#### Send Notification:
To send a notification to a specific topic, make a POST request to `/api/notifications/send` with the notification details. This will send a message to all clients subscribed to the specified topic.

### Frontend

#### Receiving Notifications:
The client application should listen for incoming FCM messages. Upon receiving a notification, it can be processed or displayed according to the application's logic.

#### Unsubscribe from Topic:
To unsubscribe from a topic, the client needs to send a request to the server, which in turn will make a call to Firebase to unsubscribe the client's token from the topic.

## API Reference

List of all available API endpoints with their functionalities:

| Endpoint                     | Method | Description                  |
|------------------------------|--------|------------------------------|
| `/api/fcm/subscribe`         | POST   | Subscribe to a topic         |
| `/api/notifications/send`    | POST   | Send a notification to a topic |

## References 
https://firebase.google.com/docs/cloud-messaging/js/send-multiple#java

