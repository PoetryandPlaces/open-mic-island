# Stanza Island

A cozy low-poly island for meeting up online. Pick a critter, wash ashore, walk around with WASD, talk on mic, type in chat, and read poems at the open mic on the wooden stage.

## How to meet up

1. Open the site. A fresh island link is made for you (it ends in `#room=…`).
2. Click **Copy** (or **Invite** once you're in) and send that link to friends.
3. Everyone who opens the same link lands on the same island.
4. Press **Turn on mic** (or `M`) to talk, and again to mute. Press `Enter` to chat.

## How it works

Everything is a single static `index.html`, so it runs on GitHub Pages with no server.

- 3D: [three.js](https://threejs.org) r149
- Networking: [Trystero](https://github.com/dmotz/trystero) 0.25.4. Browsers find each other through public Nostr relays, then positions, chat and voice go directly browser to browser over WebRTC (encrypted).
- Voice is a mesh: each person sends audio to each other person. That works well for small groups (roughly up to 8 to 10 people talking).

## Known limits

- Some strict networks (certain school, office or mobile networks) block direct WebRTC connections. If two people can see the island but not each other, add a TURN server to the `TURN` list near the top of the networking code in `index.html`.
- There are no accounts. Anyone with a room link can join that room, so share links only with people you want there.
