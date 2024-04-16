
# wannabe3

## Description

```
it seems very strange to me that he didnt call me or anything...maybe he tried to send me a message while he was trapped..can you help me in finding it..

```
## Writeup

Given the reference to being trapped, it's likely that whatever we're looking for is in trapped.md. Initially, I couldn't understand much from it:
```txt
It feels like I'm caught in a never-ending labyrinth of uncertainties, a maze of worries that twists and turns with each passing thought. The weight of the world seems to rest upon my shoulders, pressing down relentlessly, leaving me gasping for air in this suffocating embrace of anxiety. Every step I take feels like a struggle against invisible chains, dragging me deeper into a realm of isolation and fear ...

The silence that surrounds me is deafening, broken only by the echoes of my own troubled mind. I reach out, but there's nothing to grasp onto, no solid ground to anchor myself. It's as if I'm adrift in a vast ocean of insecurities, desperately searching for a lifeline that might lead me back to shore .-

Questions swirl in my head like a tempest, each one more daunting than the last ...-

What if I never find my way out of this maze? What if the darkness consumes me whole, leaving behind nothing but a hollow shell of who I once was? What if I'm destined to wander aimlessly, forever trapped in this labyrinth of fears and doubts .

The walls seem to close in with each passing moment, shrinking the space around me until there's nowhere left to turn .

I long for a glimpse of light, a beacon of hope to guide me through the darkness. But as the minutes tick by, hope feels like a distant memory, fading into the abyss along with my dreams of escape --

I yearn for the warmth of human connection, a reassuring voice to tell me that I'm not alone in this struggle .

But the silence remains unbroken, a stark reminder of my isolation. I cling to the hope that somewhere, somehow, there's a path out of this tangled maze, a way to break free from the chains that bind me. Until then, I'm left to navigate this labyrinth of worries, hoping against hope for a glimpse of daylight .
```

Then, I used the greatest tool of all time: ChatGPT. Through a lengthy chat, I discovered that the ending of each line is not so common.

After closely examining, I realized that it's Morse code written:
```
... .- ...- . . -- . . 
```

by decoding it we get "SAVEEMEE" as secreat message
## Flag

## COPS{SAVEEMEE}
