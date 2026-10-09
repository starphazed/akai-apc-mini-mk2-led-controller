# Akai APC Mini Mk2 LED Controller

A TouchDesigner project for controlling the APC Mini Mk2 LED matrix. Individual cell colour and brightness, animated backgrounds and pad-triggered effects sit together in a virtual controller interface. The demonstrations show both the software and the physical controller.

![Hands pressing the physical controller while coloured light patterns spread across its pads](documentation/screenshots/hardware-pad-response.png)

## Watch the demonstrations

| Demonstration | What it shows | Length |
|---|---|---:|
| [Hands-on pad response](https://github.com/starphazed/akai-apc-mini-mk2-led-controller/releases/download/portfolio-demos-v1/hardware-06_hands_on_pad_response.mp4) | Physical pad presses alongside changing colour patterns | 13 s |
| [Individual cell painting](https://github.com/starphazed/akai-apc-mini-mk2-led-controller/releases/download/portfolio-demos-v1/virtual-01_individual_cell_painting.mp4) | Blue cells painted onto a red matrix | 16 s |
| [Animated backgrounds](https://github.com/starphazed/akai-apc-mini-mk2-led-controller/releases/download/portfolio-demos-v1/virtual-03_animated_background_presets.mp4) | Rainbow, Center ripple and Cycle in the interface | 12 s |

[All virtual demonstrations](documentation/virtual/README.md) · [All hardware demonstrations](documentation/hardware/README.md) · [Download the video collections](https://github.com/starphazed/akai-apc-mini-mk2-led-controller/releases/tag/portfolio-demos-v1)

## Features shown

- Individual cell colour and brightness controls, painting and Fill All.
- Manual, External and Add control modes.
- Animated backgrounds and reactive Ripple and Flash controls.
- Background and reactive speed, ring width and timing adjustments.
- IMAGE / TOP input displayed on the matrix.
- Physical pad interactions with visible LED responses.

![Virtual controller with its cell editor and effect controls](documentation/screenshots/interface-overview.png)

## How it works

The project combines manual cell controls and external visual sources in the matrix processing section. Matrix data feeds the virtual preview and output path. The APC adapter connects the project to the physical controller.

```mermaid
flowchart LR
    M[Manual cell controls] --> P[Matrix processing]
    E[Effects and TOP input] --> P
    P --> V[Virtual preview]
    P --> O[Matrix data and pixel output]
    O --> A[APC adapter]
    A --> H[Physical LED matrix]
```

This diagram summarises the modules; the screenshot below shows the inspected node network.

![TouchDesigner node network and main modules](documentation/screenshots/node-network.png)

[Input, processing and output close-ups](documentation/screenshots/README.md)

## Run the project

The documented session used **TouchDesigner 2025.33230 on Windows**. Physical demonstrations use an **Akai APC Mini Mk2** connected over USB. Other versions have not been checked for this documentation.

See [project files and startup notes](project/README.md) for the current source-file status. Once the project is supplied, open its `.toe` file in TouchDesigner and keep any required media beside it using the supplied folder structure. Use the controller interface to inspect the virtual matrix. For hardware output, connect the APC Mini Mk2 and verify the intended MIDI device before enabling output.

## Documentation

| Section | Contents |
|---|---|
| [Screenshots](documentation/screenshots/README.md) | Interface, cell control, node network and processing close-ups |
| [Virtual demonstrations](documentation/virtual/README.md) | Seven short screen recordings with source times |
| [Hardware demonstrations](documentation/hardware/README.md) | Eight clips of the physical controller |
| [Capture notes](documentation/CAPTURE_NOTES.md) | Editing, evidence and limitations |

Videos are release attachments, keeping large media out of the Git history. Screenshots and documentation live in the repository.
