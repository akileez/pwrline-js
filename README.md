# pwrline-js
[![NPM version][npm-image]][npm-url]
[![build status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]
[![Downloads][downloads-image]][downloads-url]
[![js-standard-style][standard-image]][standard-url]

## Installation
```bash
$ npm install akileez\pwrline-js
```

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
   export PS1="$(~/bin/powerline.js $?)"
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

Any further arguments are presumed to be `$?` aka the error returned by the previous shell command.

No mercurial support yet and the svn support isn't good, but then, you're using git anyway. Note that I default to zsh because that's how I roll, but the original defaults to bash.

## Why?


## See Also
-

## License
[MIT](https://tldrlegal.com/license/mit-license)

[npm-image]: https://img.shields.io/npm/v/pwrline-js.svg?style=flat-square
[npm-url]: https://npmjs.org/package/pwrline-js
[travis-image]: https://img.shields.io/travis/akileez/pwrline-js.svg?style=flat-square
[travis-url]: https://travis-ci.org/akileez/pwrline-js
[coveralls-image]: https://img.shields.io/coveralls/akileez/pwrline-js.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/akileez/pwrline-js?branch=master
[downloads-image]: http://img.shields.io/npm/dm/pwrline-js.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/pwrline-js
[standard-image]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square
[standard-url]: https://github.com/feross/standard
