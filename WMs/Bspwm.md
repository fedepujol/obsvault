**Binary Space Partition Window Manager** a.k.a. **bspwm** is a true minimal tiling window manager, which allocates windows in a Fibonacci-way.

## Install

- Debian-based

```shell
apt install bspwm sxhkd
```

- Arch-based
```shell
pacman -S bspwm sxhkd
```

## Panel/Bar
Due to its minimalistic design, `bspwm` does not include a panel/bar. So its up to its user to choose and integrate it. There are several options, the most commons ones:
- polybar
- lemonbar
- dzen2

## Config
`bspwm` searches for a user defined configuration file (`bspwmrc`) inside `XDG_CONFIG_DIR/bspwm`. 

This file is auto-generated on install, and contains a set of default configurations. 

> The program being used under the hood is *bspc*.

Since we are using *bspc* the configurations are known as **rules**. Being a true minimal window manager, **bspwm**, doesn't provide a panel and a way to configure hotkeys. Its only purpose is to handle the windows.

To manage hotkey configuration, we need **sxhkd** (**S**imple **X** **H**otkey **D**aemon). Which its configuration resides in `XDG_CONFIG_HOME/sxhkd/.sxhkdrc`.

## Layout
There aren't defined layouts in **bspwm**. The windows are located based an a tree-leaf structure based on an *insertion mode*.

> By default the insertion mode is *automatic*.

### Manual mode
The user can specified the location of the new window and if its a horizontal or vertical split. This is done by sending theessage `node -p DIR`.

### Automatic Mode
It doesn't need a user choice and it's done by value of the *automatic scheme* and the default polarity value.

There are several schemes:
- Longest side
- Alternate
- Spiral