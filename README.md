# volbash

WirePlumber Control CLI wrapper for use with window manager keybindings.

Features include a volume limiter with an override toggle switch.

## Install

```
$ install -Dm 750 volbash ~/.local/bin/volbash
```

## Usage

```
Usage: volbash [OPERATION] | [OPTION]

Operations:
    up                          Increment volume
    down                        Decrement volume
    mute                        Mute volume
    unmute                      Unmute volume
    toggle                      Toggle mute

Options:
    --delta, -d VALUE           Set delta value
    --source, -s                Apply operation to source
    --bypass                    Allow increments past 100%
    --version                   Print version information
    --help                      Print this help and exit

All operations apply to the default sink only.

```

## hyprland Example

For use with a window manager like hyprland:


```
# Volume up/down
bindel = ,XF86AudioRaiseVolume, exec, volbash up
bindel = ,XF86AudioLowerVolume, exec, volbash down

# Volume up/down past 100%
bindel = SHIFT,XF86AudioRaiseVolume, exec, volbash up --bypass
bindel = SHIFT,XF86AudioLowerVolume, exec, volbash down --bypass
```

## License

[MIT License](./LICENSE)
