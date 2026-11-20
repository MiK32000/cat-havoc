# Cat Havoc

**You're a speedy cat wreaking havoc inside a house, trying not to get caught by the owner.**
Smash as much as you can, stay out of the owner's hands, and survive for one minute.

A one-file browser game built with [three.js](https://threejs.org/). No install, no build step.

## Play it

| Version | Play | Notes |
|---|---|---|
| **cat.v1** | **<https://mik32000.github.io/cat-havoc/v1/>** | First version. Every version gets its own permanent link like this one. |
| Latest | <https://mik32000.github.io/cat-havoc/> | Always the newest published version (right now that is cat.v1). |

You can also download [`index.html`](index.html) and double-click it. The game loads three.js from a CDN, so it needs an internet connection either way.

## The concept

The game started as a five-line card:

1. **You are:** a speedy cat.
2. **You can:** break things.
3. **You score when:** you break something.
4. **You lose when:** you are caught.
5. **The choice:** zooming faster helps you, but if you slip on broken items you are stunned for a second.

The rules around it: the whole game fits on one screen, a round lasts about one minute, you can play with the mouse, the arrow keys or a tap, and the score and the time left are always shown.

## How a round works

- A round lasts **60 seconds**. The clock is shown in the top-right and turns red for the last 10 seconds.
- Make it to zero without being caught and you win: **"You got away!"**
- If the owner catches you, you lose: **"Caught!"** Click, tap or press an arrow key to start over.
- Your **score** is in the top-left.

## Mechanics

**Breaking things.** Run into a vase, potted plant, lamp, mug or fish bowl and it smashes for **10 points**. There are about 24 breakable things around the house at any time, and a replacement shows up a few seconds after you break one.

**Broken bits are slippery.** Every smashed thing leaves a puddle and shards on the floor. Run over them later and you **slip, spin and are stunned for 1 second**: you can't steer while the owner closes in. Two details keep it fair:
- You never slip at the moment you break something. The pieces only become slippery after you have run clear of them.
- After you recover you are briefly safe from slipping again, so one pile can't trap you twice in a row.

**Zooming.** Hold **Space** (or hold the mouse button or your finger) to zoom at **13** instead of your normal speed of **8**. It also makes you slide more when you change direction, so zooming is faster but harder to steer around broken bits. That is the choice at the heart of the game.

**The owner.** He chases you, but he is smart about it: he aims for where you are *heading* to cut you off, and he walks round through other doors to trap you. He waits 1.5 seconds at the start, then moves just under your normal speed (7.4), so zooming is how you get away from a trap. If he touches you, you are caught.

**The house.** Three rooms (living room, kitchen, bedroom) joined by doorways in a loop, so you can always run in circles. Furniture blocks both of you, and there are no hiding spots: the owner can get to every corner.

## Controls

| Action | Keyboard | Mouse | Touch |
|---|---|---|---|
| Run | Arrow keys | Click a spot: the cat runs there (round furniture, through doors) | Tap a spot |
| Zoom | Hold **Space** | Keep the button held down (the cat also follows the pointer) | Keep your finger down |
| Start / play again | Any arrow key | Click | Tap |

## Built with

- [three.js](https://threejs.org/) r128, loaded from the cdnjs CDN
- Plain HTML, CSS and JavaScript in a single file. Floors and furniture are drawn from simple shapes at runtime, so there are no image files.
