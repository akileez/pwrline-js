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
   export PS1="$(powerline $? --depth 2) "
   export PS2="$(powerline $? --ps2 ) "
   export SPROMPT="zsh: correct %F{red}%R%f to %F{green}%r%f [nyae]? " 
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

Any further arguments are presumed to be `$?` aka the error returned by the previous shell command.

No mercurial support yet and the svn support isn't good, but then, you're using git anyway. Note that I default to zsh because that's how I roll, but the original defaults to bash.

## Why?


## See Also
-

## License
[MIT](https://tldrlegal.com/license/mit-license)

