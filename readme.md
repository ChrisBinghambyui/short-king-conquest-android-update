# Overview

I wanted to practice building a larger game catered towards mobile devices and learn the full path from writing code on a PC to running it on a real Android phone. This project is the result: a game where I learned about tile grids, conveyor-style item movement, enemy pathfinding, and saving game state.

**Short King Conquest** is an outpost builder. You dig into a mountain, mine ore, smelt it into bars, move it on conveyor belts, and sell it for credits. You spend those credits on raids, which is a bet against a rival settlement. Build towers and walls, survive every wave, and you win a payout and new land. If an enemy reaches your Gate, you only lose the buy-in.

How to use the app:

1. Build the Trade Wagon near the Gate.
2. Dig toward the ore and mine it to earn credits.
3. Build drills, smelters, and belts to automate your income.
4. Place towers outside the Gate, then press Raid to start a bet.

On a phone, one finger places the selected tool and two fingers pan and zoom. On PC, use the mouse, WASD to pan, and the scroll wheel to zoom.

[Software Demo Video](http://youtube.link.goes.here)

# Development Environment

* Android Studio Rabbit 2 | 2026.2.2 Patch 1
* Kotlin (bundled with Android Studio)
* libGDX 1.14.2
* Gradle (through the project's Gradle wrapper)
* Android SDK and Android SDK Platform-Tools, including adb (installed through Android Studio)
* Android phone with Developer options and USB debugging turned on, connected by USB cable
* Git and GitHub

# Useful Websites

* https://libgdx.com
* https://github.com/libgdx/libgdx
* https://kotlinlang.org/docs/home.html
* https://developer.android.com/studio/run/device
* https://github.com/Anuken/Mindustry

# Future Work

* Add the forest area with tree harvesting
* Add more processing chains and contracts
* Add rival-specific enemy abilities and flying enemies
* Add sound and music
* Add a phone-as-controller mode for connected PC play