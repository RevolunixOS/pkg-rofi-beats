# rofi-beats

Rofi music menu for launching a small set of internet radio and YouTube Music
sources through mpv and yt-dlp. The package installs `rofi-beats`, the
`play-music` helper, and a desktop entry.

## Build and install

```bash
nix build github:RevolunixOS/pkg-rofi-beats
nix profile install github:RevolunixOS/pkg-rofi-beats
```

Then launch:

```bash
rofi-beats
```

## Requirements

The `play-music` helper is wrapped with mpv and yt-dlp. The main menu currently
expects Rofi to be available in the session `PATH` and also expects the
adi1090x-style theme selector at:

```text
~/.config/rofi/applets/shared/theme.bash
```

The current menu contains fixed stations for Naruto, Lofi Girl, Animal
Crossing, Undertale, and the signed-in user's YouTube Music likes playlist.

## Behavior and limitations

- `play-music` restarts mpv indefinitely after playback exits.
- Starting a new source kills processes matching `radio-mpv` and `play-music`.
- The code probes a Firefox cookie database but does not currently pass it to
  yt-dlp.
- YouTube URLs and extraction behavior may change independently of this
  package.
- The script is derived from an adi1090x Rofi applet and links to the NixAchu
  adaptation in its package metadata.

## License

See [`LICENSE`](LICENSE) and retain the upstream author notices in the scripts.
