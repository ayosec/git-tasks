# git-tasks

Wrapper to use a [Taskwarrior] database per Git repository. Tasks are stored in
a `.git-tasks` directory in the top-level directory of the repository.

## Installation

1. Add `/.git-tasks/` to the `.gitignore` file.

    If you have a global file in the [`core.excludesfile`] setting, it is
    preferable to add the rule in it.

2. Add a `task` [alias] to the global configuration.

    In the global configuration file (`.config/git/config` or `~/.gitconfig`),
    the `[alias]` section should contain an entry like this:

    ```ini
    [alias]
        # …
        task = "!/path/git-tasks/git-tasks"
    ```

    `/path/git-tasks` is a copy of this repository.

    This entry can be added with `git alias`:

    ```console
    $ git config --global task '!/path/git-tasks/git-tasks'
    ```

Optionally, you can bind a key to launch `git task`. For example, to bind `git
task` to the `F1` key, add this to `~/.bashrc`:

```bash
bind -x '"\eOP": git task'
```

[Taskwarrior]: https://taskwarrior.org/
[`core.excludesfile`]: https://www.git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#_core_excludesfile
[alias]: https://www.git-scm.com/book/en/v2/Git-Basics-Git-Aliases
