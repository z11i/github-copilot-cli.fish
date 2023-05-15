# github-copilot-cli.fish
Make GitHub Copilot CLI's alias work for Fish shell. The current Copilot CLI in beta only supports bash-like syntax.

## How to install

### Via fisher

```
fisher install z11i/github-copilot-cli.fish
```

### Manually

Copy the file `conf.d/github-copilot-cli.fish` to `$__fish_config_dir/conf.d/` on your machine.

## How to use

Because Fish shell does [wildcards globbing](https://fishshell.com/docs/current/language.html#wildcards-globbing), the default aliases shipped with the CLI do not play well. Therefore I changed `?` to `!` for all aliases.

- `!!`: Translate natural language to arbitrary shell commands
- `git!`: Translate natural language to Git commands
- `gh!`: Translate natural language to GitHub CLI commands

### Use your own aliases

If you don't want the default aliases, what you can do now is to put these in your config.fish:

```
functions -e !! git! gh!
```

And use your own aliases, for example, to use `,`:

```
alias , __copilot_what-the-shell
alias ,g __copilot_git-assist
alias ,gh __copilot_gh-assist
```
