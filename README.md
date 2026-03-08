# MyUpdate - System Update Manager

A Bash script designed to simplify the process of updating various components
of your system, including the system itself, AUR, `cargo`, `npm`, and `rust`. It
provides a visual interactive menu to select the desired updates and executes
them with clear progress feedback.

---

## Features

- **Visual Interactive Menu**: Navigate with `j`/`k` or the ↑/↓ arrow keys.
  The selected option is highlighted with a `▶` pointer; unselected options
  are dimmed. Press `q` at any time to quit without selecting.
- **Box-drawing characters**: Uses Unicode box-drawing characters (┌─┐│└┘) for
  a clean, professional look.
- **Centered banner header** with title.
- **Section dividers** with arrow indicators (→) for a clean look.
- **Per-step result indicators**: each update step reports `✓ done` (green) or
  `✗ finished with errors (exit code: N)` (red) when it completes.
- **Summary panel** after batch runs with a bordered table listing the pass/fail
  status of every step.
- **Footer** showing update timestamp and terminal info.
- **Supported Updates**:
  - **System**: Updates the system using `pacman`.
  - **AUR**: Updates AUR packages using `yay`.
  - **Cargo**: Updates all installed `cargo` packages.
  - **NPM**: Updates global `npm` packages.
  - **Rust**: Updates `rust` via `rustup`.
- **Batch Updates**:
  - **All Updates**: Updates the system, AUR, `cargo`, `npm`, and `rust`.
  - **All but System/AUR**: Updates `cargo`, `npm`, and `rust` (skips system
    and AUR updates).
- **Cross-Shell Compatibility**: Works with `bash`, `sh`, and `zsh`.

---

## Navigation

| Key              | Action                        |
|------------------|-------------------------------|
| `j` or `↓`       | Move selection down (wraps)   |
| `k` or `↑`       | Move selection up (wraps)     |
| `Enter`          | Confirm selection             |
| `q` / `Q`        | Quit                          |

---

## Menu Options

| Option                | Description                                                             |
|-----------------------|-------------------------------------------------------------------------|
| **All Updates**       | Updates the system, AUR, `cargo`, `npm`, and `rust`.                    |
| **All but System/AUR**| Updates `cargo`, `npm`, and `rust` (skips system update and AUR update).|
| **System (pacman)**   | Updates the system using `sudo pacman -Syu`.                            |
| **AUR (yay)**         | Updates AUR packages using `yay -Syu`.                                  |
| **cargo packages**    | Updates all installed `cargo` packages using `cargo install-update -a`. |
| **npm global packages**| Updates global `npm` packages using `npm update -g`.                   |
| **Rust toolchain**    | Updates `rust` using `rustup update`.                                   |
| **Exit**              | Exits the script.                                                       |

---

## Requirements

- **Bash, sh, or zsh**: The script is compatible with these shell interpreters.
- **pacman**: For system updates (Arch Linux-based systems).
- **yay**: For AUR updates (Arch Linux-based systems).
- **cargo**: For Rust package management.
- **npm**: For Node.js package management.
- **rustup**: For Rust toolchain management.

---

## Customization

The script is written with my specific needs in mind, focusing on updating
system packages (via `pacman`), `aur`, `cargo`, `npm`, and `rust`. It is
designed to be easily adaptable to other use cases — add a new
`update_<tool>()` function and a corresponding entry in `menu_options` and the
`case` block.

---

## Notes

- The script assumes you are using an Arch Linux-based system for system
  updates. If you are using a different package manager, modify the
  `update_system` function accordingly.
- Ensure you have the necessary permissions to run `sudo` commands for system
  updates.

---

## License

This script is licensed under the MIT License.

```text
The MIT License (MIT)
Copyright (c) 2025-2026, Yago Mouriño Mendaña

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the “Software”), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
