# Couplet Cove

A cozy low-poly island cove for meeting up online, made by Poetry and Places. Pick a critter, wash ashore, walk around with WASD, talk on mic, type in chat, and read at the open mic on the wooden stage.

## How to meet up

1. Open the site. Without anything after the address you land in the **main lobby**, open to everyone at any time.
2. For a private meetup, pick a world under **Make a private room** on the entrance card: **Island**, **Cozy Cafe** or **Cloudy Castle**. That link ends in `#room=…`, and only people with it can find that room. The main lobby is always the island; the other worlds only exist as private rooms.
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
- `music.mp3`: the background bossa nova. `cafe-music.mp3` is the Cozy Cafe's lofi theme ("Rose Water" by massobeats). The music button opens a small panel to turn it on or off and set the music and sound-effect volumes.
- `sounds/`: recordings for critter voices, splashes, ocean waves and the campfire (see `sounds/README.md` for names and credits).
- `LICENSE`: the island is © 2026 Poetry and Places, all rights reserved (third-party parts keep their own licenses).
- `CNAME`: tells GitHub Pages to serve the site at openmic.poetryandplaces.org. Don't delete it.

## Things to do on the island

- Hop (Space) into a tree to shake it. Apple trees drop apples you can walk over to eat; they grow back. Trees with a beehive let out bees, so run!
- Press F next to a rock on the grass to dig for treasure (nets, bows, party hats, flower crowns, berets). Press B to open your bag and wear things.
- Hold the bug net and press F near fireflies to catch them.
- Dig up a fishing rod, hold it, face the ocean and press F to cast. Wait for the bite (pressing early scares the fish), press F when the bobber dips, then press F again to stop the needle in the green zone. Rarer fish are faster with smaller zones. There are four kinds, including a rare Golden Koi.
- Rocks also hide s'mores makings (marshmallows, graham crackers, chocolate). At the campfire, press F to roast a fish or toast a s'more on a stick, then eat it by the fire.
- Open your bag and press Look to watch the fireflies glowing in your jar.
- Stand next to someone and press 1, 2 or 3 to ask for a hug, a cheek kiss or a high five. They have to accept first.
- Press C to applaud. Your critter claps and everyone on the island hears it (louder the closer they are).
- Chat makes your critter's sound, and bad words are replaced with it in big red letters.
- Walk up to the microphone on the stage and press Space to take the mic. A spotlight casting the Poetry and Places logo follows you until you press Space again or step off the stage. Only one person can read at a time.
- While you read with your mic on, listeners hear a light stage echo on your voice, and you hear a softer echo of yourself. The **Stage music** panel has an on/off switch for your own echo. It sounds best with headphones.
- While you have the mic, a **Stage music** panel lets you play a song file from your computer (it streams to everyone) or paste a YouTube link (everyone's island opens the same video in a small player, started at the same point). Listeners can mute it for themselves, the reader can hide the panel with its minus button, and it stops when you finish reading. Some YouTube videos don't allow playing on other sites; those show a message instead.
- The round button in the bottom-left corner (with your critter's face) shows how to play. Press H to open it.

## The Cozy Cafe (private rooms only)

- An autumn Paris-style cafe with bistro tables (hop onto a chair to sit), a counter with a cashier, and the same open mic stage, dressed in black, with the Poetry and Places sign and spotlight.
- Three pictures on the left wall hide tools: a coffee scoop, a bamboo whisk and a bread knife. Press F by a picture to peek behind it. Tools stay in your bag.
- At the counter, press F at the espresso machine, the matcha station or the sandwich board to make coffee, a matcha latte or a sandwich, then sip or munch it.
- You can step outside onto the street, but the autumn wind is strong and blows you back in through the door.
- A library corner in the back has bean bags to sink into. Press F there to read classic public-domain poems (Shakespeare, Poe, Dickinson, Rossetti, Barrett Browning, Teasdale, Millay). Anne Carson's work is still under copyright, so the shelf has a note pointing people to her books instead.
- The cafe has its own theme song (`cafe-music.mp3`).
- A cafe link starts with `cafe-` (for example `#room=cafe-mossy-lantern-k3x9`), which is how everyone with the link lands in the cafe.

## The Cloudy Castle (private rooms only)

- A glass castle on a cloud, with rainbows and shimmering, iridescent sunshine. The open mic stage inside is pearl and gold, with the Poetry and Places sign and spotlight.
- Press F by a cloud tuft outside to dig for a magic wand or a feather quill.
- With a wand, press F at one of the two long tables to make a feast for everyone. Press F again to eat.
- With a quill, press L (or use the bag) to write a little "roses are red" letter to someone in the room. Letters are picked from a set of friendly verses, so nothing else can be sent.
- Step off the edge of the cloud and you slide down a rainbow into a pot of gold, which pops you back up to the castle.
- A castle link starts with `castle-`.

## Metrics

Visits and anonymous activity (joins, private rooms created per world, cafe tools found and drinks made, readings, fish caught, how long people stay, how many were on together, and more) go to a private GoatCounter dashboard once `GOATCOUNTER` near the top of the script in `index.html` holds your site code. Nothing personal is sent: no names, chat text or room codes. Ad blockers may hide some visits from the count.

## Copyright

© 2026 Poetry and Places. All rights reserved. See `LICENSE`.
