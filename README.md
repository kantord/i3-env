# NOT MAINTAINED

`i3-env` was an i3-specific collection of shell scripts that are no longer maintained. Check out [enwiro](https://github.com/kantord/enwiro)
wich is the successor to `i3-env` implemented in Rust.





# i3-env
Makes applications aware of your i3 workspace.

Automatically selects the correct working directory based on the workspace name.

For examples, if your active workspace is named `3: my-project`, then

```
i3-env gvim
```

will open `gvim` in `~/.i3envs/my-project`.

To use a directory different than `~/.i3envs`, simply create `~/.i3envrc` with the following contents:

```
environments_dir="~/repos"
```

When your workspace doesn't have a corresponding environment, then $HOME will be used as working directory (that's the default behavior)

## Edit multiple git branches at the same time

i3-env supports git worktrees. It means that you can have multiple workspaces of the same repo, each
assigned to a different git branch. Simply make sure that your workspaces are git repositories.


## Setup

Available in AUR: https://aur.archlinux.org/packages/i3-env/

Requires emuto to be installed: `npm install -g emuto emuto-cli`

Assuming that you have checked out the repo and the directory containing `i3-env` is in your PATH, then you can modify your bindings in your i3 configuration.

For example, this is how I launch my terminal to make it aware of the i3 context:

```
bindsym $mod+Return exec i3-env termite
```


## Automatically run commands in newly opened envs

In order to run commands in a newly opened i3-env, create a `~/.i3-env-autorun`. An example:

```
termite -e nvim
```
