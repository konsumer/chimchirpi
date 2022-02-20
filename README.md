# chimchirpi

<img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/390.png" align="right" />

This is a pi-based synthesizer, that uses a [pi in a gameboy-case](https://github.com/konsumer/chimchar-pi)

## build your own

- First setup [chimchar-pi](https://github.com/konsumer/chimchar-pi)
- add "emulationstation config" stuff, from below
- "install purr-data", from below
- copy puredata dir to ~/RetroPie/roms/puredata
- restart emulation station


### emulationstation config

```
sudo nano /opt/retropie/configs/all/emulationstation/es_systems.cfg
```

add this to bottom (inside `</systems>`)
```
<system>
    <name>puredata</name>
    <fullname>Puredata</fullname>
    <path>/home/konsumer/RetroPie/roms/puredata</path>
    <extension>.pd</extension>
    <command>purr-data -nogui -alsa -noadc -alsamidi %ROM%</command>
    <platform>ignore</platform>
    <theme>puredata</theme>
  </system>
```

### install purr-data

- find the [armv7l release](wget https://build.opensuse.org/package/binaries/home:aggraef:purr-data-git/purr-data/Raspbian_10)