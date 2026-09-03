# 🖼️ `shotctl` — macOS Screenshot Settings, From the Terminal

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![macOS](https://img.shields.io/badge/macOS-compatible-blue.svg)](https://www.apple.com/macos/)
[![Homebrew](https://img.shields.io/badge/install-homebrew-orange.svg)](https://brew.sh)

A tiny CLI for the macOS screenshot settings that are otherwise buried in
`defaults write com.apple.screencapture` incantations — format, save location,
window shadow, and filename prefix.

```bash
shotctl format jpg
shotctl location ~/Screenshots
shotctl status
```

---

## 📥 Installation

```bash
brew install sleipner01/tap/shotctl
```

That's it. Tab completions work immediately — no `.zshrc` changes needed.

To update later: `brew upgrade shotctl`.

## 🛠️ Usage

| Command | What it does |
| --- | --- |
| `shotctl format <fmt>` | Set the screenshot image format |
| `shotctl location <dir>` | Set the directory screenshots are saved to |
| `shotctl shadow <on\|off>` | Include or drop the window shadow on window captures |
| `shotctl prefix <string>` | Set the screenshot filename prefix |
| `shotctl status` | Show all current settings |
| `shotctl reset [setting]` | Restore one setting — or all of them — to the macOS default |

Plus `-h`/`--help` and `-v`/`--version`.

Every write is read back and verified, so you find out immediately if macOS
didn't take the change.

```console
$ shotctl status
com.apple.screencapture
  format    jpg
  location  /Users/you/Screenshots
  shadow    off
  prefix    Shot
```

### Supported formats

`png` · `jpg` · `jpeg` · `pdf` · `tiff` · `gif` · `bmp` · `heic`

- **PNG** — best for UI screenshots, text, graphics (lossless). The macOS default.
- **JPG/JPEG** — best for photos (lossy, much smaller files)
- **HEIC** — modern, good compression (macOS 10.13+)
- **PDF** — vector-friendly, handy for print workflows
- **TIFF** — large files, high quality (rarely needed)
- **GIF** — limited use (256 colors)
- **BMP** — uncompressed, rarely useful

An unrecognised format is passed through with a warning rather than rejected —
macOS may support formats this list doesn't know about.

## 💡 Why this tool?

I take many screenshots of **print products**, where the optimal format varies.
Switching formats lets me significantly reduce **file size** on both:

- internal servers, and
- the websites where these images are used.

This tool makes that switch instant and painless 🚀

## 📦 Requirements

macOS. Nothing else — the script runs on the zsh that ships with the system.

> **Note:** changing the save location or format affects the built-in screenshot
> UI (⌘⇧3 / ⌘⇧4 / ⌘⇧5). The `screencapture` command-line tool takes an explicit
> filename and ignores these settings.

## 🚀 Releasing

Tagging is all that's required — CI computes the checksum, bumps the Homebrew
formula in [`sleipner01/homebrew-tap`](https://github.com/sleipner01/homebrew-tap),
and cuts the GitHub release:

```bash
git tag v1.1.0 && git push origin v1.1.0
```

The `VERSION` constant in `bin/shotctl` stays `"dev"` in git — the formula
rewrites it at install time from the tag, so it can never drift.

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs or suggest features via [Issues](https://github.com/sleipner01/shotctl/issues)
- Submit pull requests for improvements
- Share feedback or use cases

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.
