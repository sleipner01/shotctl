# 🖼️ `scfmt` — Simple macOS Screenshot Format Switcher

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![macOS](https://img.shields.io/badge/macOS-compatible-blue.svg)](https://www.apple.com/macos/)
[![Shell: zsh](https://img.shields.io/badge/shell-zsh-green.svg)](https://www.zsh.org/)

A tiny CLI tool to quickly change the output format of macOS screenshots.
Useful for reducing file size depending on the type of screenshot — e.g., **PNG for graphics**, **JPG for photos**, etc.

---

## 📦 Prerequisites

- macOS
- zsh (default on macOS)
- Ability to run `defaults write` and restart `SystemUIServer` 🤓

## 📥 Installation

1. Clone the repo:

   ```bash
   git clone https://github.com/sleipner01/zsh-screenshot-format.git ~/scfmt
   ```

2. Add it to your PATH (e.g., in `~/.zshrc`):

   ```bash
   export PATH="$HOME/scfmt:$PATH"
   ```

3. Add the completion directory to your `fpath` and enable completions (in `~/.zshrc`):

   ```bash
   fpath=(~/scfmt $fpath)
   autoload -Uz compinit && compinit
   ```

4. Make the script executable:

   ```bash
   chmod +x ~/scfmt/scfmt
   ```

Reload the shell:

```bash
source ~/.zshrc
```

## 🛠️ Usage

Run the command followed by the desired format:

```bash
scfmt png
scfmt jpg
```

Show current format and help:

```bash
scfmt --help
```

Supported formats: `png`, `jpg`, `jpeg`, `gif`, `tiff`, `heic`.

### Format Recommendations

- **PNG**: Best for UI screenshots, text, graphics (lossless)
- **JPG/JPEG**: Best for photos (lossy, smaller files)
- **HEIC**: Modern format with good compression (macOS 10.13+)
- **GIF**: Limited use (256 colors, supports animation)
- **TIFF**: Large files, high quality (rarely needed for screenshots)

## 💡 Why this tool?

I take many screenshots of **print products**, where the optimal format varies.
Switching formats lets me significantly reduce **file size** on both:

- internal servers, and
- the websites where these images are used.

This tool makes that switch instant and painless 🚀

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs or suggest features via [Issues](https://github.com/sleipner01/zsh-screenshot-format/issues)
- Submit pull requests for improvements
- Share feedback or use cases

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.
