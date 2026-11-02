# volume-knob

Final project for CS193 at Purdue.

## Goal

The goal of this project is to create a physical volume mixer for my Mac.

## Problem

Currently it is annoying to change the volume of seperate apps on my Mac, oftentimes I am constantly alt tabbing between whatever game I am playing, my music, and discord to manually change the volume of each app seperately.

I find this to be very annoying, and while software exists that tries to solve this, I much prefer a tactile physical interface. Sadly though, the audio mixers that you can buy online are prohibitively expensive, often above 100 dollars, and oriented towards streamers/music producers, and contain many features I don't care about.

## Solution/MVP

I am attempting to create a simplified version of those products, the only functionality I care about is changing what source I am controlling, and then changing the volume of that specific source.

For this I am using a rotary encoder, and a button. Pressing the button toggles to the next audio source, and rotating the encoder changes its volume.

The button and encoder will be read by a microcontroller, which will then forward their input values over USB-C to my Mac. Running on my mac will be the companion app, which will read and decode the data sent over serial by the microcontroller. It will then either change the current target source, or use the Core Audio API to change the volume of the target source.

## Future Plans

In the future I would like to change the input device from an encoder to a motor. This way the knob can give haptic feedback to the user. An example of this is the motor opposing the users input if they attempt to increase the volume above 100% or below 0%.

Another future upgrade would be building an enclosure for the device, so that it has a nicer package and UI instead of a bunch of componenets stuck inside a breadboard.

## Tech Stack

- C - firmware, processing button and encoder input
- Python - Serial communication with microcontroller, testing, debugging
- Swift - MacOS companion app
- git/github - version control
- VSCode - IDE

## Project Docs

[Eisenhower Matrix](https://github.com/PatMcN7/volume-knob/blob/main/docs/eisenhower.pdf)

[System Diagram](https://github.com/PatMcN7/volume-knob/blob/main/docs/volume-knob-diagram.drawio.pdf)
