# pash-git
Simple wrapper for [dylanaraps/pash](https://github.com/dylanaraps/pash) adding git functionality similar to [pass](https://www.passwordstore.org/)

* Shellckeck compliant.
* A git commit gets created every time you add or remove password with pash.


## Dependencies

- `git`
- `[pash](https://github.com/dylanaraps/pash)`

## Configuration

The configuration is done through environemnt variables.
The script uses `$PASH_DIR` that falls back to `$XDG_DATA_HOME/pash` that falls back to `$HOME/.local/share/pash as the password store location.
You can set the pash executable path in the `$PASH_BIN` varibale. By default it assumes it's on the `$PATH`

## Usage

> I recommend aliasing `pash-git` to `pash` and adding it to `$PATH`

It's a pash wrapper, the script executes `pash` for every command except `pash-git git`

On add and del operations it will create a commit in the repository in the store after a successful `pash` call

- pash-git add web/gmail
- pash-git del web/test

Executing git commands:

- pash-git git status
- pash-git git push
- pash-git git log
