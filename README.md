# ⚡ MiroPower Control

> Windows desktop application for centralized PC power management over LAN

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://www.microsoft.com/windows)
[![Electron](https://img.shields.io/badge/Electron-27.3.11-blue.svg)](https://www.electronjs.org/)

Admin dashboard for monitoring and controlling all PCs running MiroPower Client on your local network.

![MiroPower Control Dashboard](https://via.placeholder.com/800x450?text=MiroPower+Control+Dashboard)

## ✨ Features

- 🖥️ **Real-time PC Monitoring** - Live status updates via WebSocket
- ⚡ **Power Management** - Wake, Sleep, Shutdown, Reboot commands
- 📊 **Dashboard Overview** - See all PCs, online/offline status at a glance
- 📝 **Command History** - Track all power commands sent
- 🔒 **Secure Authentication** - JWT-based login with password saving
- 🌐 **Network Detection** - Automatic detection of Wi-Fi-only devices
- 🎨 **Modern UI** - Dark theme with Tailwind CSS
- 🔄 **Auto-Update** - Built-in updater checks GitHub releases

## 📥 Installation

### Option 1: Download Release (Recommended)

1. Go to [Releases](https://github.com/YOUR_USERNAME/miropower/releases)
2. Download `MiroPower Control Setup.exe`
3. Run the installer
4. Launch from Start Menu or Desktop

### Option 2: Build from Source

**Prerequisites:**
- Node.js 18+ and npm
- Windows 10/11
- Git

**Steps:**

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/miropower.git
cd miropower/control-app

# Install dependencies
npm install

# Run in development mode
npm run dev

# Build for production
npm run build
```

The built installer will be in `dist/` folder.

## 🚀 Quick Start

1. **Launch the Application**
   - Double-click the desktop shortcut or find it in Start Menu under "MiroPower"

2. **Initial Setup**
   - Enter your MiroPower Server URL (e.g., `http://192.168.1.100:80`)
   - Login with admin credentials
   - Enable "Remember Me" to save credentials

3. **Manage PCs**
   - View all registered PCs in the grid layout
   - Click PC card for detailed information
   - Use 3-dot menu for power commands
   - Use bulk action buttons for all PCs

## 🎮 Usage

### Dashboard

The main dashboard shows:
- **Total PCs**: All registered computers
- **Online**: Currently connected PCs
- **Offline**: Disconnected PCs

### Power Commands

Available commands:
- **Wake** (Offline PCs only): Send Wake-on-LAN magic packet
- **Sleep**: Put PC into sleep mode
- **Shutdown**: Power off the PC
- **Reboot**: Restart the PC

### Bulk Actions

Three buttons at the top:
- **Shutdown All**: Power off all online PCs
- **Reboot All**: Restart all online PCs
- **Sleep All**: Put all online PCs to sleep

### PC Details

Click any PC card to view:
- Hostname and IP address
- MAC address
- Current status
- Last seen timestamp
- Connection history (last 10)
- Command history (last 10)

## 🔐 Default Credentials

- **Username**: `admin`
- **Password**: `changeme`

**⚠️ Important**: Change the default password after first login via the server configuration!

## 🔄 Auto-Updates

The app includes built-in update checking:

1. Click the 🔄 button in the footer
2. If an update is available, click "Update Now"
3. Update downloads and installs automatically
4. App restarts with the new version

## ⚙️ Configuration

### Server Connection

The app connects to your MiroPower Server. Required:
- Server URL (with port)
- Admin username
- Admin password

### Window Position

The control window:
- Appears in bottom-right corner of screen
- Width: 600px
- Max height: 900px
- Auto-adjusts height based on content

### Close on Blur

The window automatically closes when clicking outside (after 500ms delay).

## 🛠️ Development

### Tech Stack

- **Framework**: Electron 27.3.11
- **UI**: Tailwind CSS 3.x
- **HTTP**: Axios
- **WebSocket**: Native WebSocket API
- **Auto-Updater**: electron-updater

### Project Structure

```
control-app/
├── src/
│   ├── index.html      # Main UI
│   ├── renderer.js     # Frontend logic
│   ├── main.js         # Electron main process
│   └── styles.css      # Custom styles
├── assets/
│   └── icon.png        # App icon (256x256)
├── package.json        # Dependencies and build config
└── README.md           # This file
```

### Available Scripts

```bash
npm run dev         # Start in development mode
npm run build       # Build Windows installer
npm start          # Run the built app
```

### Build Configuration

The app uses electron-builder with NSIS installer:
- Desktop shortcut: ✓
- Start Menu shortcut: ✓
- Auto-start: ✗
- Per-user install: ✓
- Admin elevation: ✓ (for auto-updates)

## 🐛 Troubleshooting

### Can't connect to server

- Verify server URL and port
- Check firewall settings
- Ensure server is running
- Try pinging the server IP

### WebSocket disconnects

- Check network stability
- Verify server WebSocket is enabled
- Look for connection errors in console

### PCs not showing up

- Ensure PCs are running MiroPower Client
- Check if PCs can reach the server
- Verify authentication token is valid

### Update check fails

- Check internet connection
- Verify GitHub releases are public
- Ensure GitHub username in package.json is correct

## 📄 License

MIT License - see LICENSE file for details

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 🔗 Related Projects

- [MiroPower Server](https://github.com/YOUR_USERNAME/miropower-server) - FastAPI backend server
- [MiroPower Client](https://github.com/YOUR_USERNAME/miropower-client) - Windows client application

## 📧 Support

For issues, questions, or suggestions:
- Open an [Issue](https://github.com/YOUR_USERNAME/miropower/issues)
- Check the [Documentation](https://github.com/YOUR_USERNAME/miropower/wiki)

---

Made with ⚡ by YOUR_NAME
