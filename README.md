# Unmaintained

⚠️ This project is unmaintained. ⚠️

It is instead recommended you use `$ wpctl set-volume -l 1`.

According to this commit [here](https://github.com/PipeWire/wireplumber/commit/b1b5bf2f5f001078daf058488ed7d02101cddcf9), this
option was implemented like three years ago. Documentation didn't exist stating this option existed [until](https://github.com/PipeWire/wireplumber/commit/a5e58536dd315a0d08226fc5d4f45c871c9f8b8d#diff-3d90a93a82ce041d48bcb3c814902e6ca4010422afb26fbfebd474fed41475dd) 
like six months after this project was embarked upon, and it was not obvious the option had existed prior (or I missed it).

Either way, I'll keep this source code archived, just for the sake of showcasing some esoteric bashisms.

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
