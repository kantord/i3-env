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
