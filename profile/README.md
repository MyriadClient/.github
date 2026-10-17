<p align="center">
  <img src="https://raw.githubusercontent.com/MyriadClient/myriad-core/master/core/src/main/resources/assets/myriad/icon.png" width="96" alt="Myriad">
</p>

<h1 align="center">Myriad</h1>

<p align="center">
  An addon-first utility client for Minecraft 26.2 on Fabric.<br>
  Its menu is a tiling window manager modelled on Hyprland, every module is an addon, and the stock modules pass Grim on 2b2t.
</p>

<p align="center">
  <a href="https://myriadclient.dev">Website</a> ·
  <a href="https://github.com/MyriadClient/myriad-core/releases/latest">Download</a> ·
  <a href="https://maven.myriadclient.dev">Maven</a> ·
  <a href="https://github.com/MyriadClient/myriad-core/issues">Issues</a>
</p>

## Repositories

| | |
| --- | --- |
| [**myriad-core**](https://github.com/MyriadClient/myriad-core) | The client: the menu, the shared services (rotations, inventory, placement, breaking, elytra flight and more) and the addon API. It ships no modules of its own. |
| [**myriad-essentials**](https://github.com/MyriadClient/myriad-essentials) | The stock modules and HUD elements: Offhand, Kill Aura, Elytra Fly, Packet Mine, Scaffold, ESP, Nametags and the rest. An addon like any other. |
| [**myriad-boze**](https://github.com/MyriadClient/myriad-boze) | Every module of the Boze client in Myriad's menu, with settings, keybinds and on/off state kept in sync both ways. |
| [**myriad-omarchy**](https://github.com/MyriadClient/myriad-omarchy) | A theme that follows your Omarchy system theme. |

## Install

1. [Fabric Loader](https://fabricmc.net/use/) for Minecraft 26.2, [Fabric API](https://modrinth.com/mod/fabric-api) and Java 25.
2. Put `myriad-<v>.jar` from [core's releases](https://github.com/MyriadClient/myriad-core/releases/latest) in `mods/`,
   with `myriad-essentials-<v>.jar` from [Essentials' releases](https://github.com/MyriadClient/myriad-essentials/releases/latest)
   and any other addons.
3. In game, press **Right Shift**.

Myriad checks each addon's GitHub releases and offers updates in the menu.

## Writing an addon

Addons build against the public API (`dev.myriadclient.api`) from Myriad's maven:

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

The guide is [Writing an addon](https://github.com/MyriadClient/myriad-core#writing-an-addon) in core's README, and
[`example-addon/`](https://github.com/MyriadClient/myriad-core/tree/master/example-addon) shows every part of the API in use.

## License

Everything here is public domain under [CC0](https://creativecommons.org/publicdomain/zero/1.0/). Myriad is not
affiliated with Mojang or Microsoft.
