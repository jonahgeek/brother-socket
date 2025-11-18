# **brother-socket**

A powerful, lightweight **Socket.IO Event Inspector** built for backend engineers.
Use it to instantly connect to any Socket.IO server and **monitor all real-time events**, visualize event rates, inspect payloads, and debug connections.

Live test all incoming event data from your WebSocket server — **no setup required**.

## Features

### **Connect to Any Socket.IO Server**

- Works with local servers (`http://localhost:4000`)
- Works with remote production Socket.IO gateways
- Auto-reconnect support (if enabled on server)

### **Realtime Event Viewer**

- Displays all emitted events in real-time
- Pretty-printed JSON with syntax highlighting
- Event-type color coding
- Copy events
- Collapsible event details
- Search & filter events
- Pause/resume live feed

### **Event Analytics**

- Events-per-second chart
- Live chart updates every second
- 60-second sliding window
- Smooth transitions and responsive design

### **Fully Responsive Multi-Device UI**

- Desktop → tabbed interface
- Mobile → collapsible sidebar navigation
- Dynamic layout for phones, tablets & large screens

### **Export Tools**

- Download all captured events as JSON
- Separate system logs for connection status & diagnostics

### **Active Client Counter**

- Displays live count when your Socket.IO server emits `client_count`

## Installation

No installation needed — just clone and run in a browser.

```bash
git clone https://github.com/JonahGeek/brother-socket
cd brother-socket
```

Then open:

```
index.html
```

That's it.

## How to Use

1. Open the UI in your browser
2. Enter your Socket.IO server URL

   ```
   http://localhost:4000
   ```

3. Click **Connect**
4. Watch live events stream into the dashboard
5. Switch between **Events / Charts / System Logs**
6. Pause, filter, inspect and download logs
7. Toggle light/dark mode anytime

## Optional Server Integration

To show active client counts, emit this from your Socket.IO server:

```js
io.on("connection", (socket) => {
  io.emit("client_count", io.engine.clientsCount);

  socket.on("disconnect", () => {
    io.emit("client_count", io.engine.clientsCount);
  });
});
```

## Tech Stack

- **HTML + TailwindCSS**
- **Socket.IO Client**
- **Chart.js**
- **Vanilla JavaScript**
- Google Fonts: _Outfit_ & _Londrina Solid_

## ❤️ Built with Love

Created by [**@JonahGeek**](https://github.com/JonahGeek)

## License

MIT — use it freely for debugging, monitoring, or integrating into your internal tools.
