<p align="center">
  <img src="https://raw.githubusercontent.com/MyriadClient/myriad-core/master/core/src/main/resources/assets/myriad/icon.png" width="112" alt="Myriad logo">
</p>

<h1 align="center">Myriad</h1>

<h3 align="center">A Minecraft client built like a desktop, not a click-GUI.</h3>

<p align="center">
  Free and open source, for Minecraft 26.2 on Fabric. Made for 2b2t.
</p>

<p align="center">
  <a href="https://github.com/MyriadClient/myriad-core/releases/latest"><img src="https://img.shields.io/github/v/release/MyriadClient/myriad-core?label=download&style=for-the-badge&color=7fd4a8" alt="Download"></a>
  &nbsp;
  <a href="https://myriadclient.dev"><img src="https://img.shields.io/badge/website-myriadclient.dev-2b2d3a?style=for-the-badge" alt="Website"></a>
</p>

<br>

## Why Myriad

|  |  |
| --- | --- |
| 🪟 **A menu that tiles** | Modelled on Hyprland: nine workspaces, windows that arrange themselves, and layouts you can switch in a keystroke. Set up a combat workspace and a base workspace and flip between them. |
| ⌨️ **Find anything by typing** | A launcher searches every module, panel, theme and profile as you type. Enter turns a module on, Shift+Enter opens its settings. You rarely need the mouse. |
| 🎨 **Themes all the way down** | Colours, fonts, rounding, blur and animations, and ESP, tracers and the HUD follow the same palette, so the whole client matches. |
| 🛡️ **Made for 2b2t** | The stock modules pass Grim, 2b2t's anti-cheat, out of the box, and switch to faster behaviour on servers that don't check. |
| ⚡ **Light on your game** | A module costs nothing until it does something, and a built-in profiler shows exactly what each one costs. |
| 🧩 **Yours to shape** | Every feature is an addon. Keep the ones you want, drop the rest, add new ones from others. Updates arrive in the menu. |

<br>

## Get started

1. Install [Fabric Loader](https://fabricmc.net/use/) for Minecraft 26.2 and [Fabric API](https://modrinth.com/mod/fabric-api).
2. Download **Myriad** and **Myriad Essentials** (the modules) and drop both jars into your `mods` folder:
   - [Myriad](https://github.com/MyriadClient/myriad-core/releases/latest)
   - [Myriad Essentials](https://github.com/MyriadClient/myriad-essentials/releases/latest)
3. Start the game and press **Right Shift**.

Myriad needs Java 25, which the Minecraft launcher already includes.

<br>

## Addons

| | |
| --- | --- |
| **[Essentials](https://github.com/MyriadClient/myriad-essentials)** | The everyday modules: Offhand, Kill Aura, Elytra Fly, Packet Mine, Scaffold, ESP, Nametags, Freecam and the rest, with the HUD. |
| **[Boze](https://github.com/MyriadClient/myriad-boze)** | Already use Boze? See all of its modules in Myriad's menu, kept in sync both ways. |
| **[Omarchy](https://github.com/MyriadClient/myriad-omarchy)** | Your Omarchy desktop theme, in the menu: change themes on the desktop and Myriad follows. |

<br>

<details>
<summary><b>For developers</b></summary>

<br>

Myriad itself ([myriad-core](https://github.com/MyriadClient/myriad-core)) is the menu, the shared services (rotations,
inventory, placement, breaking, elytra flight and more) and a public addon API. It ships no modules of its own.
Essentials is built exactly like any other addon.

Addons build against the API from Myriad's maven:

```groovy
repositories {
	exclusiveContent {
		forRepositories(maven {
			name = "Myriad"
			url = "https://maven.myriadclient.dev/releases"
		})
		filter { includeGroup "dev.myriadclient" }
	}
}

dependencies {
	implementation "dev.myriadclient:myriad:0.3.0"
	// Optional: the stock modules in your dev client, to test next to them.
	localRuntime "dev.myriadclient:myriad-essentials:0.3.0"
}
```

Start with [Writing an addon](https://github.com/MyriadClient/myriad-core#writing-an-addon) in core's README.
[`example-addon/`](https://github.com/MyriadClient/myriad-core/tree/master/example-addon) uses every part of the API.
Bugs and ideas go to [issues](https://github.com/MyriadClient/myriad-core/issues).

</details>

<br>

<p align="center">
  <sub>Everything here is public domain under <a href="https://creativecommons.org/publicdomain/zero/1.0/">CC0</a>. Not affiliated with Mojang or Microsoft.</sub>
</p>
