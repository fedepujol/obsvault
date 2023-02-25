XMonad is a highly customizable tiling Window Manager written in [[Haskell]] for the X Server (X11).

## Install
Installation depends on the distro itself.  Various distro have already package *xmonad* (Debian, Arch, Fedora, Gentoo, etc).

It could be as simple as:

- Arch LInux
```shell
pacman -S xmonad xmobar xmonad-contrib
```

- Debian
```shell
apt install xmonad xmobar xmonad-contrib
```

The package *xmonad-contrib* is not strictly necessary but it offers functionalities and tools to ease and expand the configuration made for the window manager.

### Build from source
When built from source, *Xmonad* will have the latest features, fixes and bugs.

## Panel/Bar
Xmonad doesn't provide a panel/bar out of the box. The most common choice is *xmobar* which is also written in [[Haskell]] and seamless integration.

But other choices could be: *polybar*, *dzen2* and *lemonbar*.

Configuration and features are clearly distinct among the options.

## Config
Xmonad will search in the home directory for the folder *.xmonad* and inside the folder the file *xmonad.hs*. 

This behavior could be change by passing the option to the **xmonad command** to specified the configuration file.

Example config
```haskell
import Xmonad

main :: IO()
main = xmonad def
```