# Action Cable Room Demo

This is a simple Ruby on Rails project demonstrating real-time communication using Action Cable and WebSockets.  
Users can join dynamic rooms (e.g., `/rooms/1`, `/rooms/2`) and receive live messages broadcasted to each room.

## About

This project is inspired by a [YouTube tutorial](https://www.youtube.com/watch?v=t9iubpbqmnM) originally built using Rails 6.  
I recreated it using **Rails 7**, incorporating modern conventions and the `importmap` setup.  
It serves as a learning experiment for understanding Action Cable and WebSocket channels in Rails.

## Features

- Connects to a room channel based on the room ID in the URL
- Subscribes to a custom channel with `room_id` parameter
- Receives real-time messages from the server
- Console-based message display (can be extended)

## Getting Started

### 1. Install Ruby

Make sure you are using **Ruby 3.4.2**.

### 2. Clone the repository

```bash
git clone https://github.com/casconeluca/ac-explorer.git
cd ac-explorer
```
### 3. Install Redis (required for Action Cable) 

For **macOS users**, you can install Redis with Homebrew:

```bash
brew install redis
brew services start redis
```

For other operating systems (e.g., Linux, Windows), refer to the official [Redis installation guide](https://redis.io/download).

### 4. Install gems

```bash
bundle install
```

### 5. Start the app

```bash
bin/rails s
```

### 6. Open in browser

Go to:

```
http://localhost:3000/rooms/1
```

Open multiple tabs to simulate users in the same room.

### 7. Broadcast a message (Rails console)

```ruby
ActionCable.server.broadcast("room_channel_1", { message: "Hello from server!" })
```

The message will appear in the browser console of all clients connected to that room.

