# pwrline-js

## Installation
```sh
$ npm install akileez\pwrline-js
```
should install `powerline` in your node path. Or clone the repo & symlink `powerline.js` to some location in your path.

Then go to the [original most excellent project page](https://github.com/powerline/powerline) or [find a patched font you like](https://github.com/powerline/fonts).

## Usage
Use it as you would the original. E.g, for bash:

```sh
function _update_ps1() {
   export PS1="$(~/bin/powerline.js $? --shell bash --depth 4)"
}
export PROMPT_COMMAND="_update_ps1"
```

For zsh:

```sh
function powerline_precmd()
{
   export PS1="$(powerline $? --depth 2 --hostname) "
   export PS2="$(powerline $? --ps2 ) "
}
precmd_functions=(powerline_precmd)
```

## Options

`--shell [zsh|bash]`  
: which shell to emit color escapes for; defaults to `'zsh'`

`--cwd-only`  
: use only the current working directory in the prompt; defaults to `false`

`--mode [patched|compatible]`  
: which font mode to expect; defaults to `'patched'`

`--depth *N*`  
: how many segments of the current working directory to show; defaults to 5

`--no-repo`  
: do not attempt to show extra source repository information for the current directory; defaults to `false`

`--repo-only`  
: generate *only* a source repository segment; defaults to `false`

`--ps2`  
: generate a ps2 segment powerline style

`--hostname`  
: generate a hostname segment. defaults to `false`

Any further arguments are presumed to be `$?` aka the error returned by the previous shell command.

No mercurial support yet and the svn support isn't good, but then, you're using git anyway. Note that I default to zsh because that's how I roll, but the original defaults to bash.

## Customize the colors

Use the following environment variables in order to override the default segment colors:

segment | environment variable
-----|---------------------
hostname | `POWERLINE_HOSTNAME_BG`, `POWERLINE_HOSTNAME_FG`
path | `POWERLINE_PATH_BG`, `POWERLINE_PATH_FG`, `POWERLINE_CWD_FG`, `POWERLINE_SEPARATOR_FG`
git repo status | `POWERLINE_REPO_CLEAN_BG`, `POWERLINE_REPO_CLEAN_FG`, `POWERLINE_REPO_DIRTY_BG`, `POWERLINE_REPO_DIRTY_FG`
command status | `POWERLINE_CMD_PASSED_BG`, `POWERLINE_CMD_PASSED_FG`, `POWERLINE_CMD_FAILED_BG`, `POWERLINE_CMD_FAILED_FG`
subversion status | `POWERLINE_SVN_CHANGES_BG`, `POWERLINE_SVN_CHANGES_FG`
virtual python environment name | `POWERLINE_VIRTUAL_ENV_BG`, `POWERLINE_VIRTUAL_ENV_FG`


Example:

```sh
# Configure powerline
export POWERLINE_REPO_CLEAN_BG=149
export POWERLINE_REPO_CLEAN_FG=0
export POWERLINE_REPO_DIRTY_BG=160
export POWERLINE_REPO_DIRTY_FG=250
```

## Why?


## See Also
-

## License
[MIT](https://tldrlegal.com/license/mit-license)

