
## Pipewire

`sudo pacman -Syu && sudo pacman -S pipewire pipewire-pulse pipewire-jack pipewire-alsa && systemctl --user enable --now pipewire pipewire-pulse && systemctl --user enable --now wireplumber `

```

If JACK applications do not automatically detect the PipeWire JACK implementation, you may need to set the `PIPEWIRE_JACK_COMPAT` variable or ensure correct links are established for JACK libraries.
```