# Modern Escape Room Chat Application

A Python-based, room-based chat application with client-server architecture, persistent chat history, and modern GUI built using Tkinter. The project demonstrates network communication, multi-threading, and data persistence for a real-time group chat experience.

## 🚀 Project Overview

Escape Room implements a real-time chat system where users can create or join named chat rooms and communicate through a GUI client. The server manages multiple rooms, broadcasts messages, and maintains per-room chat histories saved to disk.

## ✨ Key Features

### 🌐 Client-Server Architecture
- **Server**: Handles multiple client connections, room creation/joining, message broadcasting, and history persistence
- **Client**: GUI application to create/join rooms, send/receive messages, and display chat history

### 🏷️ Room Management
- Create new chat rooms or join existing ones
- Server maintains active room registry
- Clients receive prior chat history upon joining a room

### 💾 Persistent Chat History
- Chat histories are stored as JSON files in `chat_history/` directory
- History automatically loaded on room creation/joining and saved on new messages

### 📨 Real-Time Messaging
- **Multi-threaded**: Separate threads for message receiving to keep GUI responsive
- **Broadcasting**: Server broadcasts messages to all clients in the room
- **Graceful Exit**: Clean disconnection with leave and exit commands

### 🎨 Modern GUI Client
- Built with **Tkinter** and **ttk** for cross-platform desktop UI
- **Login & Room Selection**: User-friendly interface for username and room input
- **Chat Interface**: Scrollable chat window, message input, and navigation controls
- **Built-in Validations**: Error dialogs for invalid actions, connection issues, and user prompts

## 📁 Project Structure

```
chat2_0/
├── client/
│   ├── client2_0.py          # Main GUI client application
│   ├── client2_0.spec        # PyInstaller spec for client executable
│   ├── build/client2_0/      # PyInstaller build artifacts
│   └── dist/                 # PyInstaller distribution with client executable
├── server/
│   ├── server2_0.py          # Main server application
│   ├── server2_0.spec        # PyInstaller spec for server executable
│   ├── build/server2_0/      # PyInstaller build artifacts
│   └── dist/                 # PyInstaller distribution with server executable
├── chat_history/             # Directory for JSON-based chat histories
└── README.md                 # Project documentation
```

## 🛠️ Technical Stack

- **Language**: Python 3.8+
- **GUI**: Tkinter (ttk)
- **Networking**: Python `socket` library
- **Concurrency**: `threading` module for asynchronous message handling
- **Data Persistence**: JSON files for room chat history
- **Build Tool**: PyInstaller for packaging executables

## 💡 Getting Started

### Prerequisites

- Python 3.8 or higher
- Required packages (install via pip):
  ```bash
  pip install pillow
  ```

### Running the Server

1. Navigate to the server directory:
   ```bash
   cd chat2_0/server
   ```
2. Run the server application:
   ```bash
   python server2_0.py [host] [-p port]
   ```
   - Default host: `127.0.0.1`
   - Default port: `5000`

### Running the Client

1. Navigate to the client directory:
   ```bash
   cd chat2_0/client
   ```
2. Run the client application:
   ```bash
   python client2_0.py
   ```
3. In the GUI:
   - Enter a **Username** and **Room** name
   - Click **Create Room** to start a new room
   - Or **Join Room** to enter an existing room

## 🎯 Usage Guide

### Creating a Room
1. Launch the client GUI
2. Enter a unique username and new room name
3. Click **Create Room**
4. Wait for server confirmation and chat history loading

### Joining a Room
1. Launch the client GUI
2. Enter your username and existing room name
3. Click **Join Room**
4. Previous chat history for the room is displayed

### Sending Messages
- Type your message in the input field
- Press **Enter** or click **Send**
- Messages are timestamped and broadcast to room participants

### Leaving and Exiting
- Click **Back to Login** to leave the room
- Click **Exit** to close the application entirely
- The server cleans up empty rooms automatically

## 🗄️ Chat History

- Chat history for each room is stored in `chat_history/<room>.json`
- On room creation or joining, the history file is loaded and sent to the client
- New messages are appended and saved in real-time

## 🏗️ Packaging with PyInstaller

Preconfigured spec files allow building standalone executables:

```bash
# Client executable
cd client
pyinstaller client2_0.spec

# Server executable
cd ../server
pyinstaller server2_0.spec
```

Executables are placed in the `dist/` directory for easy distribution.

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature-name`)
3. Commit your changes and push to your branch
4. Open a Pull Request detailing your enhancements

## 🐛 Troubleshooting

- **Connection Errors**: Ensure the server is running and host/port match
- **Timeouts**: Increase socket timeout or network reliability
- **Room Not Found**: Create the room first before joining
- **JSON Errors**: Check `chat_history/` folder permissions and file integrity

## 📄 License

This project is licensed under the **MIT License**. See [LICENSE](../LICENSE) for details.

---

*Built with ❤️ leveraging Python networking and GUI for immersive chat experiences*
