# === Tmux ===

<Pr> = prefix (C-s)

# Getting started

| command                     | action                      |
|-----------------------------|-----------------------------|
| `tmux`                      | start new session           |
| `tmux new -s name`          | start new session with name |
| `tmux a`                    | attach to a session         |
| `tmux a -t name`            | attach to a session name    |
| `tmux ls`                   | list sessions               |
| `tmux kill-session -t name` | Kill session                |


# Sessions

|-------------|-----------------------|
| command     | action                |
|-------------|-----------------------|
| `<Pr>:new`  | new session           |
| `<Pr>$`     | name session          |
| `<Pr>s`     | list session          |
| `<Pr>( / )` | previous/next session |
| `<Pr>L`     | Last session          |

# Windows

|-----------|----------------------------|
| Keybind   | Action                     |
|-----------|----------------------------|
| `<Pr>$ c` | Create new window          |
| `<Pr>$ w` | List windows               |
| `<Pr>$ f` | Find window                |
| `<Pr>$ ,` | Name window                |
| `<Pr>$ &` | Kill window                |
| `<Pr>$ n` | Next window                |
| `<Pr>$ p` | Previous window            |
| `<Pr>$ l` | Previously selected window |


# Pane

|-------------|---------------------------------------------------------------|
| Keybind     | Action                                                        |
|-------------|---------------------------------------------------------------|
| `<Pr>%`     | Vertical split                                                |
| `<Pr>"`     | Horizontal split                                              |
| `<Pr>o`     | Switch focus between panes                                    |
| `<Pr>q`     | Show pane numbers                                             |
| `<Pr>x`     | Kill pane                                                     |
| `<Pr>z`     | Toggle active pane between zoomed and unzoomed                |
| `<Pr>"+`    | Break pane into window (e.g. to select text by mouse to copy) |
| `<Pr>"+"`   | Restore pane from window                                      |
| `<Pr>Space` | Toggle between layouts                                        |
| `<Pr>{`     | Move the current pane left                                    |
| `<Pr>}`     | Move the current pane right                                   |

# Copy mode

Copy mode allows to copy inside the current buffer with most vim keys.
|---------|-----------------|
| Keybind | Action          |
|---------|-----------------|
| <Pr>[   | enter copy mode |
| hjkl    | move cursor     |
| space   | start selection |
| enter   | copy selection  |

# Command

## Resizing panes

|------------------------------------|---------------------------------------------------|
| Command                            | Description                                       |
| ---------------------------------- | ------------------------------------------------- |
| resize-pane -D ##                  | Resize the current pane down by ## lines.         |
| resize-pane -U ##                  | Resize the current pane up ## lines.              |
| resize-pane -L ##                  | Resize the current pane left ## lines.            |
| resize-pane -R ##                  | Resize the current pane right ## lines.           |
| resize-pane -y ##                  | Resize the current pane to ## lines tall.         |
| resize-pane -x ##                  | Resize the current pane to ## lines wide.         |


# Other

|---------|---------------|
| keybind | action        |
|---------|---------------|
| `<Pr>d` | detach        |
| `<Pr>t` | big clock     |
| `<Pr>?` | list shortcut |
