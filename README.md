# Collaborative Shopping### Technical Details

### Architecture
- **Frontend**: Vue.js 3 (loaded from CDN)
- **WebRTC**: PeerJS library for peer-to-peer connections
- **Signaling**: PeerJS free cloud signaling servers
- **Storage**: Browser localStorage for persistence
- **Styling**: Custom CSS with responsive designA real-time collaborative shopping list application built with Vue.js and WebRTC for peer-to-peer synchronization.

## Features

- ✅ Create new shopping lists or join existing ones
- ✅ Add, remove, and mark items as collected
- ✅ Real-time synchronization between multiple clients
- ✅ Offline persistence using localStorage
- ✅ No server required - works entirely client-side
- ✅ Responsive design for mobile and desktop
- ✅ Share lists using simple codes

## How to Use

1. **Open the app**: Simply open `index.html` in any modern web browser
2. **Create a new list**: Click "Create New List" and give it a name
3. **Share the list**: Copy the generated share code and send it to others
4. **Join a list**: Click "Join Existing List" and enter a share code
5. **Add items**: Type in the input field and press Enter or click Add
6. **Mark items**: Check the checkbox to mark items as collected
7. **Remove items**: Click the trash icon to delete items

## Technical Details

### Architecture
- **Frontend**: Vue.js 3 (loaded from CDN)
- **Synchronization**: localStorage-based peer discovery (simulates WebRTC signaling)
- **Storage**: Browser localStorage for persistence
- **Styling**: Custom CSS with responsive design

### How Synchronization Works
The app uses **PeerJS** for true WebRTC peer-to-peer communication:

1. **Peer Discovery**: PeerJS provides free signaling servers for initial connection setup
2. **Direct Communication**: Once connected, all data flows directly between browsers (no server)
3. **Real-time Sync**: Changes are instantly broadcast to all connected peers
4. **Conflict Resolution**: Timestamps are used to resolve conflicts between concurrent edits
5. **Automatic Merging**: Items from different clients are automatically merged

### Data Persistence
- Each shopping list is saved to localStorage
- Lists persist even when all clients are offline
- When clients reconnect, they automatically sync their changes

## Browser Compatibility
- Works in all modern browsers (Chrome, Firefox, Safari, Edge)
- Requires JavaScript enabled
- Uses modern browser APIs (localStorage, clipboard API)

## Usage Tips
- Keep the browser tab open to maintain connection with other peers
- Multiple people can add/edit items simultaneously across different devices
- Items marked as "collected" will appear crossed out
- The app shows connection status and number of connected peers
- Peer IDs are case-sensitive and unique to each session
- Works across different networks and locations

## Limitations
- Depends on PeerJS free signaling service (has usage limits)
- Some corporate/school firewalls may block WebRTC connections
- Limited to browser storage capacity for offline persistence
- Peer connections are temporary (lost when browser is closed)

## File Structure
```
shopping/
├── index.html          # Complete application (HTML + CSS + JS)
├── package.json        # Project metadata
└── README.md          # This file
```

## Future Enhancements
- Custom signaling server for better reliability
- User authentication and persistent accounts
- Shopping list templates
- Item categories and organization
- Price tracking and budgets
- Shopping history
- Voice/video chat integration
- Push notifications for list updates