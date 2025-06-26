# TCP_Chat_App

#  How the Real-Time Chat App Works

This is a simple real-time chat application built using **Flask** and **Flask-SocketIO**. It allows users to create or join chat rooms using unique codes and exchange messages in real-time.

---

##  Workflow Overview

1. **User Enters Home Page**
   - Enters their name.
   - Can either:
     - Join a room using a code.
     - Create a new room (a unique 4-letter code is generated).

2. **Room Management**
   - Each room is stored in memory with:
     - `members` count
     - `messages` list
   - If a room becomes empty, it is automatically deleted.

3. **Session Tracking**
   - User info (name and room) is stored using Flask sessions.

4. **Chat Room**
   - Displays the current room code and chat messages.
   - Users can send messages in real time using a WebSocket connection.
   - Previous messages (from memory) are loaded on room join.

5. **Real-Time Messaging**
   - Powered by Flask-SocketIO and Socket.IO JS client.
   - Messages are broadcasted to all users in the same room.
   - On disconnect, a message is sent and the user is removed from the room.

---

##  Internals

- **Frontend**: HTML + JS + Socket.IO client
- **Backend**: Flask + Flask-SocketIO
- **Transport**: WebSockets (over TCP)
- **Storage**: In-memory Python dictionary (no database)

---

## Notes

- This is a temporary chat system — data is not persisted.
- All communication (HTTP + WebSockets) is over **TCP**.
