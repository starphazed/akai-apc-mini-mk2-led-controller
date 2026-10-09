# Project files and startup

| File | Use | Saved MIDI state |
|---|---|---|
| [apc_mini_mk2_effects.tox](apc_mini_mk2_effects.tox) | Reusable component; recommended starting point | Disabled |
| [APC_Mini_mk2_Layer_Controls.toe](APC_Mini_mk2_Layer_Controls.toe) | Complete demo | Enabled; may send immediately |

## Requirements

The documented environment is Windows with TouchDesigner **2025.33230**. According to the supplied setup guide, virtual editing, effects and TOP conversion work without hardware. Physical output uses an **Akai APC Mini Mk2** over USB. Other versions, platforms and controllers have not been verified for this distribution.

The reusable export contains its operators and Python DATs. No development scripts or external Python packages are required in the documented environment. Custom media sources may introduce file dependencies; no user video is bundled.

## Open the interface

1. Download and extract the repository.
2. Drag `apc_mini_mk2_effects.tox` into a TouchDesigner network.
3. Enter `lighting_matrix_demo` (its name may be suffixed if one already exists).
4. Right-click `controller_ui` and choose **View**. The matrix component's **Open Clickable Preview** pulse also opens the panel.
5. Click **Effect settings** for the layer settings.

Alternatively, open the `.toe` directly. It is saved with MIDI enabled. Avoid two active copies writing to the same controller.

## Edit cells and run effects

Choose **Manual**, click a pad, set RGB and brightness, then click **Apply Cell**. **Fill All** writes the editor value to all 64 pads. **Clear Manual** clears the stored manual board. **Paint** applies the editor values when a virtual or physical pad is pressed.

Selecting a background or reactive preset selects **External** mode. Return to **Manual** to see stored edits. **Effect settings** contains layer speed/intensity, ring width and timing controls. Faders display physical input; they are not draggable lighting controls.

## Connect the hardware

1. Connect the APC Mini Mk2 over USB.
2. In `apc_mini_mk2_adapter`, check **MIDI Device Name** (`Devicename`). The documented name is `APC mini mk2`, using the main port rather than its second MIDI port.
3. Click **Connect APC**. The adapter uses its own device map, not the global MIDI Mapper.
4. Press a pad or move a physical fader and observe the interface.

**Resend** retransmits the current pad and small-button states. **MIDI Off** disables input/output but does not send a blackout; LEDs may retain their last state. Click **Connect APC** after reconnecting the USB device. Status and packet counts report local activity, not hardware acknowledgement.

## Use a TOP source

Inside `lighting_matrix_demo/media_input`, replace the `media_example` connection with a TOP output, then choose **IMAGE / TOP** in the controller. For a file, use a Movie File In TOP. Keep custom media paths portable when sharing the project.

The existing setup guide describes a generated orientation pattern as the included example. Input stretches to square; crop or letterbox upstream if needed. Playback speed belongs to the source TOP, not the background speed slider.

## Provenance and verification

Both files were copied byte-for-byte from the supplied project folder on 9 October 2026. SHA-256 hashes matched the originals. The originals were not opened, modified or resaved during publication. Startup guidance was checked against the existing setup documentation; no new runtime test was performed during publishing.

The earlier capture session used a numbered `.1.toe` save. This repository includes the unnumbered project supplied for distribution; it is not asserted to be byte-identical to the recorded save.

| File | SHA-256 |
|---|---|
| APC_Mini_mk2_Layer_Controls.toe | `56c101670ac62c87b3b6f0e8f05ea5fdb8d161fda9bfcf1ae5da943761e15b85` |
| apc_mini_mk2_effects.tox | `951a99eeba8651da4fd84d467850894dade0047ccc433e6991d50c114c85a059` |
