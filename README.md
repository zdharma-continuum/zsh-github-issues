# zsh-github-issues

Subscribe to your projects of interest on Github and receive **within shell** (under prompt) notifications about new
issues and pull requests.

# Usage

The tool currently needs Zsh and [zinit](https://github.com/zdharma-continuum/zinit).

## Manual ice-specifying

The notificator load:

```zsh
zinit ice lucid id-as'GitHub-notify' \
        ice on-update-of'~/.cache/zsh-github-issues/new_titles.log' \
        notify'New issue: $NOTIFY_MESSAGE'
zinit light zdharma-continuum/zsh-github-issues
```

Background daemon load (it pulls the issues, by default every 2 minutes):

```zsh
# GIT stands for 'Github Issue Tracker', the future name of the project
GIT_PROJECTS=zdharma-continuum/zsh-github-issues:zdharma/zinit

zinit ice service"GIT" pick"zsh-github-issues.service.zsh" wait'2' lucid
zinit light zdharma-continuum/zsh-github-issues
```

## Pulling ices from the Zplugin packages

Recent Zplugin supports packages which hold the needed ices. To install the plugin from them, issue:

```zsh
zinit pack for @github-issues
zinit pack for @github-issues-srv
```

# Screenshot

![screenshot](https://raw.githubusercontent.com/zdharma-continuum/zsh-github-issues/master/img/git.png)

<!-- vim:set tw=89: -->
