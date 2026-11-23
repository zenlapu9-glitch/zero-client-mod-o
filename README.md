# ZERO CLIENT — Fabric 1.21.11 (Initial source release)

This is an initial Fabric client-mod source project for **Minecraft Java 1.21.11**. It targets Java 21 and Fabric API `0.141.1+1.21.11`.

## Implemented in this source release (source-level; compile/runtime not yet verified)

- **Right Shift:** opens the ZERO CLIENT click GUI.
- **Zoom (C):** while the Zoom module is enabled, hold C to temporarily set the FOV to 30 degrees; the original FOV is restored when released.
- **Toggle Sprint:** holds the vanilla sprint key while forward is pressed. It does not change server movement packets.
- **FPS HUD:** displays the current frame rate.
- **Coordinates HUD:** displays block X/Y/Z.
- **Direction HUD:** displays the facing direction.
- **Ping Display:** displays local player latency when connected to a multiplayer server.
- **Keystrokes HUD:** displays W/A/S/D and jump key state.
- **Click GUI:** touch/mouse-friendly category tabs, searchable module descriptions, toggle states, and scrolling.
- **Config persistence:** module enabled states are stored in `config/zero-client.properties`.

The HUD elements are rendered through Fabric's `HudElementRegistry` API, not the deprecated `HudRenderCallback`.

## Not implemented in this release

The following requested feature families are **not present** in this initial build: KillAura, Aim Assist, TriggerBot, Auto Clicker, Reach, Velocity, Criticals, Hitbox Expansion, automated combat, flight/speed/phase cheats, ESP/chams/X-ray, automated inventory actions, a full HUD drag editor, color pickers, profile management, and the remaining long-list modules. They are not represented as fake toggles. This release intentionally limits functionality to the working modules listed above.

No anti-cheat bypass, stealth, or evasion code is included.

## Build requirements

- JDK 21
- Gradle 9.9.1 (or a compatible Gradle 9.x installation)
- Internet access to resolve Fabric/Minecraft Gradle dependencies

From this project directory, run:

```bash
gradle build
```

The remapped distributable JAR should be created under `build/libs/` with the project name and version. Do not install a `-sources` JAR or a `-dev` JAR.

## Android / Zalith installation

After a successful build, copy the remapped `zero-client-0.1.0.jar` from `build/libs/` to the `mods` folder of the **Minecraft 1.21.11 Fabric** instance in Zalith Launcher 2. Install a matching Fabric API build (`0.141.1+1.21.11`) in that instance as well. Keep a backup of the instance before testing.

The click GUI is opened with Right Shift by default. The key can be rebound from Minecraft's Controls screen. Once open, the GUI accepts tap/click input.

## Verification status for this handoff

- Source files and metadata: created.
- JSON metadata syntax: checked by the handoff script.
- Gradle compilation: **not run** in this environment because the `gradle` executable is not installed. No dependency resolution or compiler verification was possible.
- Fabric Loader validation: not run.
- Zalith Launcher 2 / Android runtime test: not run.

This ZIP is the source project, **not an installable JAR**. Do not rename it to `.jar` or place the ZIP in the mods folder.
