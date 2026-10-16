# Couplet Cove

A cozy low-poly island cove for meeting up online, made by Poetry and Places. Pick a critter, wash ashore, walk around with WASD, talk on mic, type in chat, and read at the open mic on the wooden stage.

## How to meet up

1. Open the site. Without anything after the address you land in the **main lobby**, open to everyone at any time.
2. For a private meetup, click **Make a private island** on the entrance card. That link ends in `#room=…`, and only people with it can find that island.
3. Click **Copy** (or **Invite** once you're in) and send the link to friends. Everyone who opens the same link lands on the same island.
4. Press **Turn on mic** (or `M`) to talk, and again to mute. Press `Enter` to chat.

## How it works

Everything is a single static `index.html`, so it runs on GitHub Pages with no server.

- 3D: [three.js](https://threejs.org) r149
- Networking: [Trystero](https://github.com/dmotz/trystero) 0.25.4. Browsers find each other through public Nostr relays, then positions, chat and voice go directly browser to browser over WebRTC (encrypted).
- Voice is a mesh: each person sends audio to each other person. That works well for small groups (roughly up to 8 to 10 people talking).

## Known limits

- Some strict networks (certain school, office or mobile networks) block direct WebRTC connections. The island includes a Metered TURN credential (the `TURN` list in `index.html`) so those players connect through a relay instead. Manage or rotate it in the Metered dashboard under TURN Server → Credentials; if you rotate it, paste the new username and credential into the `TURN` list.
- Players find each other through the Nostr relays in the `RELAYS` list. If several of them go offline someday, swap in other public relays.
- There are no accounts. Anyone can walk into the main lobby, and anyone with a private island link can join that island, so share private links only with people you want there.
- Voice and positions go directly between browsers, so a very busy main lobby (more than about 10 to 12 people) can get choppy. For bigger events, use a private island per group.

## Files

- `index.html`: the whole island.
- `music.mp3`: the background bossa nova. The music button opens a small panel to turn it on or off and set the music and sound-effect volumes.
- `sounds/`: recordings for critter voices, splashes, ocean waves and the campfire (see `sounds/README.md` for names and credits).
- `CNAME`: tells GitHub Pages to serve the site at openmic.poetryandplaces.org. Don't delete it.

## Things to do on the island

- Hop (Space) into a tree to shake it. Apple trees drop apples you can walk over to eat; they grow back. Trees with a beehive let out bees, so run!
- Press F next to a rock on the grass to dig for treasure (nets, bows, party hats, flower crowns, berets). Press B to open your bag and wear things.
- Hold the bug net and press F near fireflies to catch them.
- Stand next to someone and press 1, 2 or 3 to ask for a hug, a cheek kiss or a high five. They have to accept first.
- Press C to applaud. Your critter claps and everyone on the island hears it (louder the closer they are).
- Chat makes your critter's sound, and bad words are replaced with it in big red letters.
- Walk up to the microphone on the stage and press Space to take the mic. A spotlight follows you until you press Space again or step off the stage. Only one person can read at a time.
- While you have the mic, a **Stage music** panel lets you play a song file from your computer (it streams to everyone) or paste a YouTube link (everyone's island opens the same video in a small player, started at the same point). Listeners can mute it for themselves, and it stops when you finish reading. Some YouTube videos don't allow playing on other sites; those show a message instead.
- The round button in the bottom-left corner (with your critter's face) shows how to play. Press H to open it.
