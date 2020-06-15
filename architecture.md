drawing web app
 - mobile first
 - raw js
 - websockets
   - recv full game state
   - send drawing
   - send vote

game host web app
 - desktop first
 - raw js
 - websockets
   - recv full game state
   - recv images
   - send control signals (like exit game)

server
 - python
 - http handlers
   - index
   - /create (for game host)
   - /join (landing page for players)
   - /game (takes a room code and a player name) 
 - websocket
   - recv image from drawing app
   - recv vote from drawing app
   - recv control signals from game host app
   - send game state (delta?) whenever it changes
   - send images to game host
 - database? nah, let's store everything in memory.