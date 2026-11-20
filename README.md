# Cat Havoc

**You're a speedy cat wreaking havoc, trying not to get caught by the owner.**
Smash as much as you can and stay out of the owner's hands, in a big house or in a park cut up by canals.

A one-file browser game built with [three.js](https://threejs.org/). No install, no build step.

## Play it

Every version has its own permanent link, so an older version never changes when a new one comes out.

| Version | Play | Notes |
|---|---|---|
| **cat.v2** | **<https://mik32000.github.io/cat-havoc/v2/>** | Second version: 9-room house, a park, three game modes, a main menu, Cat cam and new controls. See the update notes below. |
| cat.v1 | <https://mik32000.github.io/cat-havoc/v1/> | First version, exactly as it was released: one small three-room house and a 60-second round. |
| Latest | <https://mik32000.github.io/cat-havoc/> | Always the newest published version (right now that is cat.v2). |

You can also download [`index.html`](index.html) and double-click it. The game loads three.js from a CDN, so it needs an internet connection either way.

## The concept

The game started as a five-line card:

1. **You are:** a speedy cat.
2. **You can:** break things.
3. **You score when:** you break something.
4. **You lose when:** you are caught.
5. **The choice:** zooming faster helps you, but if you slip on broken items you are stunned for a second.

The rules around it: the whole game fits on one screen, you can play with the mouse, the arrow keys or a tap, and the score is always shown.

## Update notes

### cat.v2: what's new

**A much bigger house**
- The house grew from 3 rooms to **9**: Kitchen, Dining room, Study, Living room, Grand hall, Bedroom, Bathroom, Playroom and Garage. They are joined by short corridors, and **every room has at least 2 ways in and out**, so you can always run in loops. The house is about four times the area of the old one.
- The camera shows **one room at a time** and glides to the next room as you walk into a corridor. The rooms around it stay visible.
- Far more obstacles for the owner to go round: furniture, pillars, plants, crates, barrels and stools, plus crate pairs with a gap only the cat can squeeze through. A check at build time removes any clutter that would leave a spot the owner can't reach, so there are no safe hiding places.

**A second map: the Park**
- A square park inside a brick wall, split into 6 areas by **canals**, with wooden **bridges** joining them (every area has at least 2 bridges).
- Benches, trees, bushes, flowerbeds, picnic tables, fountains and rocks play the part of the house's walls and furniture.
- It has its own breakable things: flower pots, garden gnomes, glass lanterns, bottles and bird baths.

**Three game modes** (pick one on the main menu)
- **Classic:** the one-minute round from cat.v1.
- **Break everything:** no timer and no respawns. You win when every single thing in the map is broken (54 in the house, 42 in the park). Being caught still ends it.
- **Endless:** no timer and no end. Keep breaking things until the owner catches you. The score screen shows how long you lasted.

**Cat cam** (an on/off switch on the main menu)
- The camera follows the cat all the time instead of showing a whole room.
- The whole map stays loaded, and everything **fades smoothly into view** as the cat gets closer and fades back into darkness as it moves away (nothing pops in).
- You can see an area of 32 by 23 world units around the cat, with the middle 22 by 13 fully clear. The limit is measured in the game's own units, so zooming the web page or resizing the window can't show more of the map.

**Main menu**
- The title screen has dropdowns for **Map** and **Mode**, a **Cat cam** on/off switch and a Play button.
- Behind it plays a looping animation: you sit on the couch in the living room, with a high beamed ceiling and a spinning fan, while the cat is chased through the house (into the kitchen and the hall too) by the owner. Every room has the same high ceiling, and the doorways are tall arches the owner can walk through.
- Keyboard shortcuts: **1 / 2** pick the map, **3 / 4 / 5** pick the mode, **C** toggles Cat cam, **Enter** or **Space** plays.
- During a round the **MENU** button (or **Esc**) takes you back to the menu. After a round, the result card has **Play again** and **Main menu** buttons.
- The corner counter changes with the mode: time left, things left, or time survived.

**New things to watch for**
- **The owner can slip too.** Each time he steps on broken bits he has a 1 in 5 chance of tripping and being stunned for 2 seconds. A tripped owner can't catch you.
- **Broken bits clean themselves up** 10 seconds after they are broken.
- **Breakable things glow yellow** (a soft pulsing halo and a ring on the floor), so you can tell what you can smash.
- **Sprinting leaves a wind trail:** white streaks follow the cat while it zooms.
- **The cat gets scared.** When the owner is within about 9 units its fur turns spiky and its tail puffs up and stands straight up.

**New controls** (both ways of playing are always available, there is no setting)
- **WASD** or the **arrow keys** run the cat, and **Space** sprints.
- Use only the **mouse** and the cat follows the cursor; hold the **left mouse button** to sprint. The cursor becomes a **red dot** while the mouse is steering.
- On touch screens the cat follows your finger, and a second finger down sprints.
- The cat is much smoother round furniture and corners: it plans its route with a wider margin, its body is a little slimmer against obstacles, it eases its steering, and it slows down as it reaches the cursor.

**Smaller changes**
- The owner waits 2 seconds at the start of a round (it was 1.5), because the maps are bigger.
- Breakable things only appear where the cat can really get to them, so "Break everything" can always be finished.

### cat.v1: first version
- One small house with three rooms (living room, kitchen, bedroom) in a loop, 60-second rounds, click or tap to run, hold Space (or the mouse or your finger) to zoom, and an owner that cuts you off.

## How a round works

- **Classic:** you have **60 seconds**. The clock is in the top-right and turns red for the last 10 seconds. Reach zero without being caught and you win: **"You got away!"**
- **Break everything:** smash every last thing in the map to win: **"You broke everything!"**
- **Endless:** survive as long as you can. The game ends when you are caught.
- If the owner catches you in any mode you lose: **"Caught!"** Press a movement key, click or tap to play again, or go back to the main menu.
- Your **score** is in the top-left.

## Mechanics

**Breaking things.** Run into a vase, potted plant, lamp, mug or fish bowl (in the park: a flower pot, gnome, lantern, bottle or bird bath) and it smashes for **10 points**. There are 6 breakable things in every room of the house and 7 in every area of the park. In Classic and Endless a replacement shows up in the same room a few seconds after you break one; in Break everything nothing comes back.

**Broken bits are slippery.** Every smashed thing leaves a puddle and shards on the floor. Run over them later and you **slip, spin and are stunned for 1 second**: you can't steer while the owner closes in. They vanish after 10 seconds. Two details keep it fair:
- You never slip at the moment you break something. The pieces only become slippery after you have run clear of them.
- After you recover you are briefly safe from slipping again, so one pile can't trap you twice in a row.

**Sprinting.** Hold Space (or the left mouse button) to sprint at **13** instead of your normal speed of **8**. It also makes you slide more when you change direction, so sprinting is faster but harder to steer round broken bits. That is the choice at the heart of the game.

**The owner.** He chases you, but he is smart about it: he aims for where you are *heading* to cut you off, and he walks round through other doors to trap you. He waits 2 seconds at the start, then moves just under your normal speed (7.4), so sprinting is how you get away from a trap. If he touches you, you are caught. If he steps on broken bits he may trip (1 in 5) and be stunned for 2 seconds.

**The maps.** The house has 9 rooms and the park has 6 areas, and in both you can always run in circles. Furniture, trees, canals and walls block both of you, and there are no hiding spots: the owner can get to every corner.

## Controls

| Action | Keyboard | Mouse | Touch |
|---|---|---|---|
| Run | **WASD** or the arrow keys | Move the mouse: the cat follows the cursor (round furniture, through doors) | The cat follows your finger |
| Sprint | Hold **Space** | Hold the **left button** (**Space** works too) | Put a second finger down |
| Start / play again | Enter or Space on the menu; a movement key on the result card | Click **PLAY** / **Play again** | Tap **PLAY** / **Play again** |
| Back to the menu | **Esc** (or **M** on the result card) | The **MENU** button | The **MENU** button |

On the main menu, **1 / 2** pick the map, **3 / 4 / 5** pick the mode and **C** switches Cat cam on and off.

## Built with

- [three.js](https://threejs.org/) r128, loaded from the cdnjs CDN
- Plain HTML, CSS and JavaScript in a single file. Floors and furniture are drawn from simple shapes at runtime, so there are no image files.
