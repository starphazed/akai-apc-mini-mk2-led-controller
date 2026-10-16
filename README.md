# Akai APC Mini Mk2 LED Controller

A TouchDesigner project for controlling the APC Mini Mk2 LED matrix. Individual cell colour and brightness, animated backgrounds and pad-triggered effects sit together in a virtual controller interface. The demonstrations show both the software and the physical controller.

![Hands pressing the physical controller while coloured light patterns spread across its pads](documentation/screenshots/hardware-pad-response.png)

## Watch the demonstrations

### Hands-on pad response · 13 seconds

Physical pad presses alongside changing colour patterns.

https://github.com/user-attachments/assets/f1cd376a-3594-4a91-a08f-d45accc9b276

### Individual cell painting · 16 seconds

Blue cells painted onto a red matrix while surrounding cells retain their colour.

https://github.com/user-attachments/assets/a60ef4d3-5085-47da-9d3e-1c54ca11b447

### Animated backgrounds · 12 seconds

Rainbow, Center ripple and Cycle selected in the virtual interface.

https://github.com/user-attachments/assets/ae592db3-9781-49d3-a0ce-e4bc30e3dd84

The hardware video above is a compressed preview. Original-quality clips and the complete collections remain available below.

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

1. Download the repository with **Code → Download ZIP**, then extract it.
2. Recommended: drag [`apc_mini_mk2_effects.tox`](project/apc_mini_mk2_effects.tox) into a TouchDesigner network. This reusable component starts with MIDI disabled.
3. Enter the imported `lighting_matrix_demo` component, right-click `controller_ui`, and choose **View**.
4. Select **Manual** to edit cells, or choose a background and a reactive effect.
5. For physical output, connect the APC Mini Mk2 over USB, verify the device name, then click **Connect APC**.

Alternatively, open [`APC_Mini_mk2_Layer_Controls.toe`](project/APC_Mini_mk2_Layer_Controls.toe) for the complete demo. **The `.toe` is saved with MIDI enabled and may send immediately.** Use only one active adapter per controller.

[Full startup and media-input instructions](project/README.md). No external Python packages or development scripts are needed for the supplied component in the documented environment. These binaries were copied unchanged; a fresh TouchDesigner launch was not performed during publication.

## Documentation

| Section | Contents |
|---|---|
| [Screenshots](documentation/screenshots/README.md) | Interface, cell control, node network and processing close-ups |
| [Virtual demonstrations](documentation/virtual/README.md) | Seven short screen recordings with source times |
| [Hardware demonstrations](documentation/hardware/README.md) | Eight clips of the physical controller |
| [Capture notes](documentation/CAPTURE_NOTES.md) | Editing, evidence and limitations |

Featured videos play inline through GitHub attachments; the full collections are release downloads. Large media stays out of the Git history. Screenshots and documentation live in the repository.

## License and credits

The original custom project content and associated written documentation are licensed under the [MIT License](LICENSE), copyright (c) 2026 starphazed. Preserve the license when redistributing the component or source.

TouchDesigner is developed by Derivative; the APC Mini Mk2 is an Akai Professional product. Their software, assets and trademarks retain their own terms. Development used OpenAI Codex with human feedback and physical-controller checks. See [third-party notices and scope](THIRD_PARTY_NOTICES.md).
