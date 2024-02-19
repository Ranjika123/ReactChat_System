
React+firebase chat System
# React Chat System with Firebase

![Chat System Screenshot](screenshot.png)

## Overview

Welcome to the React Chat System repository! This project is a full-stack chat application built using React for the front end and Firebase for the backend. It provides real-time chat functionality and can be easily integrated into various web applications.

## Features

- **Real-Time Chat:** Enjoy real-time messaging with other users.

- **User Authentication:** Users can sign up, log in, and customize their profiles.

- **Multiple Chat Rooms are Dleted:** Becuase FBI warned me about BOYS CHATS 

- **Message History:** Access chat history and scroll back through messages.

- **Responsive Design:** The chat system is responsive, ensuring a seamless experience on various devices.

## Getting Started

To run this chat system locally or deploy it, follow these steps:

### Prerequisites

- Node.js installed on your machine.
- A Firebase project set up with Authentication and Realtime Database services enabled.

### Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/Ranjika123/ReactChat_System.git
   ```

2. Navigate to the project directory:

   ```bash
   cd react-chat-system
   ```

3. Install the project dependencies:

   ```bash
   npm install
   ```

4. Set up Firebase:
   - Create a Firebase project on the [Firebase Console](https://console.firebase.google.com/).
   - Configure Firebase in your project by adding your Firebase configuration to `src/firebase.js`.

5. Start the development server:

   ```bash
   npm start
   ```

6. Open your web browser and navigate to [http://localhost:3000](http://localhost:3000) to view the chat system locally.
7. Build a "Build" Folder By Running
   ```bash
   npm run build
   ```
8.Update the App.js According to you API Key and Data


## Usage

- Sign up or log in to your account.
- Join or create chat rooms.
- Start sending and receiving messages in real-time.

## Deployment

To deploy this chat system to a hosting service, follow the deployment guidelines for your chosen platform (e.g., Firebase Hosting, Netlify, Vercel).
 ```bash
   firebase deploy
   ```

## Firebase  Server Rules
   ```bash
   rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
  
    match /{document=**} {
      allow read, write: if false;
    }
    
    match /messages/{docId} {
      allow read: if request.auth.uid != null;
      allow create: if canCreateMessage();
    }
    
    function canCreateMessage() {
      let isSignedIn = request.auth.uid != null;
      let isOwner = request.auth.uid == request.resource.data.uid;
      
      let isNotBanned = !exists(/databases/$(database)/documents/banned/$(request.auth.uid));
      return isSignedIn && isOwner && isNotBanned;
    }
  }
}
   ```
### Update It Under rules sectopn in firebase-database✔ 

### IF Errors occured that you can't fix use eslint
```bash
{
  "plugins": ["firebase"],
  "extends": [
    "eslint:recommended",
    "plugin:firebase/eslintrc"
  ],
  "rules": {
    "firebase/no-duplicate-names": "warn",
    "firebase/no-redundant-rules": "warn",
    "firebase/prefer-use-app": "warn",
    "firebase/valid-app-options": "warn",
    "firebase/valid-auth-required": "warn",
    "firebase/valid-credential-type": "warn",
    "firebase/valid-download-size": "warn",
    "firebase/valid-emulator-config": "warn",
    "firebase/valid-get-data": "warn",
    "firebase/valid-location": "warn",
    "firebase/valid-on-complete": "warn",
    "firebase/valid-permissions": "warn",
    "firebase/valid-set-data": "warn",
    "firebase/valid-update-data": "warn"
  }
}
```

## Contributing

If you'd like to contribute to this project, please fork this repository, make your changes, and create a pull request. We welcome enhancements and bug fixes!

## Authors

- **Name** - [Ranjika Nethpriya](https://github.com/Ranjika123/)
- **social** - [Facebook](https://web.facebook.com/ranjikaneth/)
- **social**- [Instergrame](https://www.instagram.com/ranjika_neth/)

## License

This project is open-source and available under the [MIT License](LICENSE).

## Acknowledgments

We'd like to thank the React and Firebase communities for their valuable contributions to web development.

```

Dont violate our community guid lines,You will banned for rest of your life or Your Syster gonna pregnet 
