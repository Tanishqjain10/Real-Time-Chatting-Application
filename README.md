# 💬 Real-Time Chatting Application

A **Real-Time Chatting Application** built using **Java Swing and Socket Programming**. The project demonstrates client-server communication, real-time message exchange, GUI development, and multithreading in Java.

The project contains two applications:

* **One-to-One Chatting Application** — real-time communication between a client and server.
* **Group Chatting Application** — allows multiple clients to communicate through a centralized server.

---

## 🚀 Features

### One-to-One Chat

* Real-time message exchange between two users
* Client-server architecture
* Java Socket Programming
* Interactive Java Swing GUI
* Message timestamps
* WhatsApp-inspired chat interface
* Send messages using the **Send** button
* Real-time incoming message display
* Custom icons and user profiles

### Group Chat

* Supports multiple connected clients
* Centralized group chat server
* Real-time message broadcasting
* Multithreaded client handling
* Every connected client receives broadcast messages

---

## 🛠️ Technologies Used

| Technology             | Purpose                              |
| ---------------------- | ------------------------------------ |
| **Java**               | Core programming language            |
| **Java Swing**         | Graphical User Interface             |
| **Socket Programming** | Real-time network communication      |
| **TCP/IP**             | Client-server communication          |
| **Multithreading**     | Handling multiple group-chat clients |
| **NetBeans**           | Project development                  |
| **Apache Ant**         | Project build system                 |

---

## 🏗️ Project Architecture

### One-to-One Chat

```text
┌─────────────────┐       TCP Socket       ┌─────────────────┐
│                 │ ─────────────────────> │                 │
│     Client      │                        │     Server      │
│   Java Swing    │ <───────────────────── │   Java Swing    │
│                 │       Messages         │                 │
└─────────────────┘                        └─────────────────┘
```

The client connects to the server using a TCP socket. Messages are exchanged using Java's `DataInputStream` and `DataOutputStream`.

### Group Chat

```text
                    ┌──────────────┐
                    │    Server    │
                    │  Port 2003   │
                    └──────┬───────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
     ┌────▼────┐      ┌────▼────┐      ┌────▼────┐
     │ Client 1│      │ Client 2│      │ Client 3│
     └─────────┘      └─────────┘      └─────────┘
```

The group chat server creates a separate thread for each connected client and broadcasts received messages to all connected users.

---

## 📂 Project Structure

```text
chatting-application-master/
│
├── Chatting Application/
│   ├── src/
│   │   ├── chatting/
│   │   │   └── application/
│   │   │       ├── Client.java
│   │   │       └── Server.java
│   │   │
│   │   └── icons/
│   │       ├── 1.png
│   │       ├── 2.png
│   │       ├── 3.png
│   │       ├── phone.png
│   │       ├── video.png
│   │       └── ...
│   │
│   ├── nbproject/
│   ├── build.xml
│   └── manifest.mf
│
├── Group Chatting Application/
│   ├── src/
│   │   ├── group/
│   │   │   └── chatting/
│   │   │       └── application/
│   │   │           ├── Server.java
│   │   │           ├── UserOne.java
│   │   │           ├── UserTwo.java
│   │   │           └── UserThird.java
│   │   │
│   │   └── icons/
│   │
│   ├── nbproject/
│   ├── build.xml
│   └── manifest.mf
│
└── README.md
```

---

# ⚙️ How to Run

## Prerequisites

Make sure you have:

* **Java JDK 17 or later**
* NetBeans IDE (recommended)
* Basic knowledge of Java networking

Check your Java installation:

```bash
java -version
```

---

# 💻 Running the One-to-One Chat

### Step 1 — Open the Project

Open the following folder in NetBeans:

```text
Chatting Application
```

### Step 2 — Start the Server

Run:

```text
chatting.application.Server
```

The server starts a `ServerSocket` on:

```text
Port: 6001
```

### Step 3 — Start the Client

Run:

```text
chatting.application.Client
```

The client connects to:

```text
127.0.0.1:6001
```

### Step 4 — Start Chatting

Type a message in the input field and click:

```text
Send
```

Messages will be transmitted through the TCP socket and displayed in real time.

---

# 👥 Running the Group Chat

### Step 1 — Start the Group Server

Run:

```text
group.chatting.application.Server
```

The server listens on:

```text
Port: 2003
```

### Step 2 — Start Multiple Users

Run the user classes:

```text
UserOne
UserTwo
UserThird
```

Each user connects to the group server.

### Step 3 — Send Messages

When one user sends a message, the server broadcasts it to all connected clients.

---

# 🔌 Networking

## One-to-One Chat

The application uses:

```java
ServerSocket
Socket
DataInputStream
DataOutputStream
```

The server listens for incoming connections:

```java
ServerSocket skt = new ServerSocket(6001);
```

The client connects using:

```java
Socket s = new Socket("127.0.0.1", 6001);
```

Messages are transmitted using:

```java
dout.writeUTF(message);
```

and received using:

```java
din.readUTF();
```

---

## 👥 Multithreading in Group Chat

The group chat server uses Java threads to handle multiple users.

For every new client connection:

```java
Socket socket = s.accept();
Server server = new Server(socket);
Thread thread = new Thread(server);
thread.start();
```

This allows multiple clients to communicate with the server simultaneously.

---

# 🎨 User Interface

The application uses **Java Swing** to create a WhatsApp-inspired interface containing:

* User profile
* Online status
* Chat messages
* Message timestamps
* Send button
* Phone icon
* Video icon
* Custom application icons

---

# 🧠 Concepts Demonstrated

This project demonstrates several important Java concepts:

* Object-Oriented Programming
* Java Swing
* Event Handling
* Client-Server Architecture
* Socket Programming
* TCP/IP Communication
* Input/Output Streams
* Multithreading
* Exception Handling
* GUI Component Design
* Network Communication

---

# 🔮 Future Improvements

The current application can be extended with:

* 🔐 User authentication and login
* 💾 Database integration
* 📨 Message history
* 👤 User registration
* 🟢 Online/offline status
* 📎 File sharing
* 🖼️ Image sharing
* 🎙️ Voice messages
* 📞 Voice calling
* 📹 Video calling
* 🔔 Desktop notifications
* 🔒 End-to-end encryption
* ☁️ Cloud deployment
* 📱 Mobile application

---


Example:

```markdown
![Chat Application](screenshots/chat-window.png)
```

---

# 📌 Key Learning

The main objective of this project is to understand how **real-time communication works using Java networking**.

The project combines **Java Swing for the frontend** with **Socket Programming for real-time communication**, while the group chat demonstrates how **multithreading can be used to handle multiple clients simultaneously**.

---

# 👨‍💻 Author

**Tanishq Jain**

* GitHub: [Tanishqjain10](https://github.com/Tanishqjain10)
* LinkedIn: [Tanishq Jain](https://www.linkedin.com/in/tanishqjain10/)

---

## ⭐ If you found this project useful

Give this repository a ⭐ on GitHub!
