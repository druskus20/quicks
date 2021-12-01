# Zsh snippets

#### Change cursor shape for VI mode
This functions changes your cursor character based on the current VI mode
(`|` for INSERT mode, `█` for NORMAL mode).
```zsh
cursor_mode() {
    cursor_block='\e[2 q'
    cursor_beam='\e[6 q'

    function zle-keymap-select {
        if [[ ${KEYMAP} == vicmd ]] ||
            [[ $1 = 'block' ]]; then
            echo -ne $cursor_block
        elif [[ ${KEYMAP} == main ]] ||
            [[ ${KEYMAP} == viins ]] ||
            [[ ${KEYMAP} = '' ]] ||
            [[ $1 = 'beam' ]]; then
            echo -ne $cursor_beam
        fi
    }

    zle-line-init() {
        echo -ne $cursor_beam
    }

    zle -N zle-keymap-select
    zle -N zle-line-init
}

cursor_mode
```

source: [thevaluable.dev](https://thevaluable.dev/zsh-install-configure/)


#### Rebuild completion cache

```sh
rm -i ${ZDOTDIR:-${HOME:?No ZDOTDIR or HOME}}/.zcompdump &&
compinit
```

source: [stackexchange](https://unix.stackexchange.com/questions/2179/rebuild-auto-complete-index-or-whatever-its-called-and-binaries-in-path-cach)
