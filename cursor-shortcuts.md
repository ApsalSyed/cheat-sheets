# Cursor Keyboard Shortcuts

This document provides a list of common keyboard shortcuts for the Cursor editor.
For a complete and always up-to-date reference, please see the [official Cursor documentation](https://docs.cursor.com/kbd).

**Note:** For Windows and Linux users, `Cmd` can generally be replaced with `Ctrl`.

## General Shortcuts

| Shortcut          | Action                                  |
| ----------------- | --------------------------------------- |
| `Cmd + I`         | Toggle Sidepanel (unless bound to mode) |
| `Cmd + L`         | Toggle Sidepanel (unless bound to mode) |
| `Cmd + .`         | Open Mode Menu                          |
| `Cmd + /`         | Loop between AI models                  |
| `Cmd + Shift + J` | Open Cursor settings                    |
| `Cmd + ,`         | Open General settings                   |
| `Cmd + Shift + P` | Open command palette                    |

## Chat Shortcuts

These shortcuts work when the chat input box is focused.

| Shortcut                               | Action                       |
| -------------------------------------- | ---------------------------- |
| `Enter`                                | Submit                       |
| `Cmd + Shift + Backspace`              | Cancel generation            |
| `Cmd + L` (with code selected)         | Add selected code as context |
| `Cmd + Shift + L` (with code selected) | Add selected code as context |
| `Cmd + Enter`                          | Accept all changes           |
| `Cmd + Backspace`                      | Reject all changes           |
| `Tab`                                  | Cycle to next message        |
| `Shift + Tab`                          | Cycle to previous message    |
| `Cmd + Alt + /`                        | Open model toggle            |
| `Cmd + N` / `Cmd + R`                  | Create new chat              |
| `Cmd + T`                              | Create new chat tab          |
| `Cmd + [`                              | Open previous chat           |
| `Cmd + ]`                              | Open next chat               |
| `Cmd + W`                              | Close chat                   |
| `Esc`                                  | Unfocus the field            |

## Cmd+K (Inline Edit) Shortcuts

| Shortcut                  | Action             |
| ------------------------- | ------------------ |
| `Cmd + K`                 | Open               |
| `Cmd + Shift + K`         | Toggle input focus |
| `Enter`                   | Submit             |
| `Cmd + Shift + Backspace` | Cancel             |
| `Option + Enter`          | Ask quick question |

## Code Selection & Context Shortcuts

| Shortcut                                  | Action                               |
| ----------------------------------------- | ------------------------------------ |
| `@`                                       | @-symbols (for context)              |
| `#`                                       | Files (for context)                  |
| `/`                                       | Shortcut Commands                    |
| `Cmd + Shift + L`                         | Add selection to Chat                |
| `Cmd + Shift + K`                         | Add selection to Edit                |
| `Cmd + L`                                 | Add selection to new chat            |
| `Cmd + M`                                 | Toggle file reading strategies       |
| `Cmd + →` (right arrow)                   | Accept next word of suggestion       |
| `Cmd + Enter`                             | Search codebase in chat              |
| Select code, `Cmd + C`, `Cmd + V`         | Add copied reference code as context |
| Select code, `Cmd + C`, `Cmd + Shift + V` | Add copied code as text context      |

## Tab Autocompletion Shortcuts

| Shortcut                | Action            |
| ----------------------- | ----------------- |
| `Tab`                   | Accept suggestion |
| `Cmd + →` (right arrow) | Accept next word  |

## Terminal Shortcuts

| Shortcut      | Action                   |
| ------------- | ------------------------ |
| `Cmd + K`     | Open terminal prompt bar |
| `Cmd + Enter` | Run generated command    |
| `Esc`         | Accept command           |

## Advanced Shortcuts

### Navigation & Selection

| Shortcut          | Action                    |
| ----------------- | ------------------------- |
| `Cmd + Shift + O` | Go to symbol in file      |
| `Cmd + P`         | Quick file navigation     |
| `Cmd + Shift + P` | Command palette           |
| `Cmd + B`         | Toggle sidebar visibility |
| `Cmd + J`         | Toggle panel visibility   |
| `Cmd + Shift + E` | Focus on explorer         |
| `Cmd + Shift + F` | Focus on search           |
| `Cmd + Shift + X` | Focus on extensions       |
| `Cmd + Shift + G` | Focus on source control   |
| `Cmd + Shift + D` | Focus on debug            |

### Multi-cursor & Selection

| Shortcut            | Action                         |
| ------------------- | ------------------------------ |
| `Cmd + D`           | Select next occurrence         |
| `Cmd + Shift + L`   | Select all occurrences         |
| `Cmd + U`           | Undo last cursor operation     |
| `Cmd + Shift + K`   | Delete line                    |
| `Cmd + Shift + ↑/↓` | Move line up/down              |
| `Cmd + Alt + ↑/↓`   | Add cursor above/below         |
| `Cmd + Shift + I`   | Add cursor to end of each line |

### Code Folding & Navigation

| Shortcut                | Action              |
| ----------------------- | ------------------- |
| `Cmd + Option + [`      | Fold code block     |
| `Cmd + Option + ]`      | Unfold code block   |
| `Cmd + K` `Cmd + 0`     | Fold all            |
| `Cmd + K` `Cmd + J`     | Unfold all          |
| `Cmd + K` `Cmd + [0-9]` | Fold to level [0-9] |

### Split Editor

| Shortcut              | Action                              |
| --------------------- | ----------------------------------- |
| `Cmd + \`             | Split editor right                  |
| `Cmd + K` `Cmd + \`   | Split editor down                   |
| `Cmd + K` `Cmd + ←/→` | Focus on previous/next editor group |
| `Cmd + K` `Cmd + ↑/↓` | Focus on editor group above/below   |

### AI-Specific Advanced Shortcuts

| Shortcut            | Action                   |
| ------------------- | ------------------------ |
| `Cmd + K` `Cmd + I` | Generate inline code     |
| `Cmd + K` `Cmd + C` | Add comment to selection |
| `Cmd + K` `Cmd + D` | Generate documentation   |
| `Cmd + K` `Cmd + T` | Generate test            |
| `Cmd + K` `Cmd + R` | Refactor code            |
| `Cmd + K` `Cmd + F` | Fix code issues          |

---

_This cheat sheet is based on information available as of late 2023/early 2024. Shortcuts may change; always refer to the official Cursor documentation for the latest keybindings._
