Setting up ZSH
==============

I recently spent a couple of hours transitioning from Bash to ZSH, from Terminal.app to iTerm2, and generally modifying my custom settings. Here are the important notes:

- I setup a custom ZSH prompt. It's not overbearing, and it's a little less feature packed than some of the other [available ZSH themes][zsh-themes], but I like it. Here's the code I'm using:

    ```bash
    function get_host {
        echo `hostname`
    }

    CIARAND_PATH_='%{$fg[blue]%}%~%{$reset_color%}'
    CIARAND_HOST_='%{$fg[red]%}@%{$reset_color%}%{$fg[blue]%}$(get_host)%{$reset_color%}'
    CIARAND_GIT_='%{$fg_bold[magenta]%}$(git_prompt_info)%{$reset_color%}'
    PROMPT="%{$fg[red]%}⚡%{$reset_color%}:"
    RPROMPT="$CIARAND_GIT_ $CIARAND_PATH_$CIARAND_HOST_"

    ZSH_THEME_GIT_PROMPT_DIRTY=" %{$fg_bold[red]%}●%{$reset_color%}"
    ZSH_THEME_GIT_PROMPT_CLEAN=" %{$fg[blue]%}●%{$reset_color%}"
    ZSH_THEME_GIT_PROMPT_PREFIX="%{$fg_bold[magenta]%}\ue0a0 "
    ZSH_THEME_GIT_PROMPT_SUFFIX=""
    ```

- I changed color schemes to [Tomorrow Night Eighties][tne]
- I remapped my Vim `<LeaderKey>` and began adding some shortcuts, beginning with:

    ```bash
    " Leader, h1 underlines the line in = (h1 in MD)
    nnoremap h1 VypVr=
    " Leader, h2 underlines the line in - (h2 in MD)
    nnoremap h2 VypVr-
    ```

I'm planning on creating my own fork of [oh-my-zsh][omz] to keep these changes, let me know via [App.net][adn] if you have any comments or additions!

[zsh-themes]: https://github.com/robbyrussell/oh-my-zsh/wiki/themes "A listing of many oh-my-zsh themes"
[tne]: https://github.com/chriskempson/tomorrow-theme "Tomorrow Night, a theme by @chriskempson"
[omz]: https://github.com/robbyrussell/oh-my-zsh "Oh My Zsh, a ZSH framework"
[adn]: https://alpha.app.net/ciarand/ "Ciaran's App.net profile"
