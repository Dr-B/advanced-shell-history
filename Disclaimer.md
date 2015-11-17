## Disclaimers: ##

### Intents ###
  * this is _not_ intended to become a security tool - it's meant only for enhancing the default shell history

### `bash` Users ###
  * default history settings are modified
    * `HISTCONTROL` is zeroed out to disable the `ignoredups` and `ignorespace` options
    * `HISTTIMEFORMAT` is set to `"%s "` to make it possible to calculate command duration
  * your existing `PROMPT_COMMAND` variable will be renamed
    * if you already define a `PROMPT_COMMAND` function, it will be renamed to `ASH_PROMPT_COMMAND` and executed _after_ the command has been logged
  * `PIPESTATUS` is renamed `ASH_PIPESTATUS`

### `zsh` Users ###
  * your default history settings will be modified
    * extended history will be enabled via `setopt extended_history`
    * immediate history-file appending will be enabled by `setopt inc_append_history`
    * if `SAVEHIST` is less than 1, it will be bumped up to 1
  * `pipestatus` is renames `ASH_PIPESTATUS`