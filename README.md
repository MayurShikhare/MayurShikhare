# Welcome 🤗

Hola! Yo soy Mayur, a software engineer specializing in front-end development with React and Next.js.  
I have 5+ years of professional experience (AEM - 2Y, React - 3Y+) building intuitive and maintainable web applications.

- I enjoy optimizing developer workflows  
- Experimenting with productivity tools like Zsh, Git aliases, and terminal enhancements
- 👀 Interested in technologies and design in general.
- 🌱 currently building AURA - your financial intelligence.
- 📫 you can find more about me on -> [HERE](https://mayur-shikhare.netlify.app/)


This repository contains my personal configuration and Git alias setup to help streamline everyday development tasks.

View the full `.zshrc` file [here](https://github.com/MayurShikhare/MayurShikhare/blob/main/.zshcrc) or scroll to read more.

### My Zsh Configuration

### Git Aliases - some of the most used Git aliases

```bash
alias gs='git status'
alias gl='git log --oneline'
alias glog='git log'
alias glg='git log --graph --oneline --all --decorate'
alias gaa='git add .'
alias gcm='git commit -m'
alias gpsh='git push'
alias gpl='git push'
alias grbi='git rebase -i'
alias grb-main='git rebase origin/main'
alias grbi-root='git rebase -i --root'
alias gabort='git rebase --abort'
alias gcontinue='git rebase --continue'
alias gsoft='git reset --soft'
alias ghard='git reset --hard'
alias gcmundo='git reset --soft HEAD~1'
alias grestore='git restore'
alias grestoreall='git restore .'
alias guns='git restore --staged'
alias gunsa='git restore --staged .'
alias gsh='git stash'
alias gshapply='git stash apply'
alias gshpop='git stash pop'
alias gshls='git stash list'
alias gshcl='git stash clear'
alias gb='git branch'
alias gbr='git branch -r'
alias gba='git branch -a'
alias gco='git checkout'
alias gcb='git checkout -b'
alias gcl='git clone'
alias gdf='git diff'
alias gdfc='git diff --cached'
alias gsta='git status -s'
alias gcount='git shortlog -sn'
alias gfixup='git commit --fixup'
alias gsquash='git rebase -i --autosquash'
alias gtag='git tag'
alias gtags='git tag -l'
alias gshow='git show'
alias gfetch='git fetch'
alias gfetchall='git fetch --all'
alias gmerge='git merge'
alias gundo='git reset HEAD~1'
```



### Descriptions

```bash
alias_desc[gs]="Show git status"
alias_desc[gl]="Shortcut: git log --oneline"
alias_desc[glog]="Git log"
alias_desc[glg]="Git log graph & decorate"
alias_desc[gaa]="Stage all changes"
alias_desc[gcm]="Commit with message"
alias_desc[gpsh]="Push to remote"
alias_desc[gpl]="Push to remote"
alias_desc[grbi]="Interactive rebase"
alias_desc[grb-main]="Rebase onto origin/main"
alias_desc[grbi-root]="Interactive rebase from root"
alias_desc[gabort]="Abort rebase"
alias_desc[gcontinue]="Continue rebase"
alias_desc[gsoft]="Soft reset"
alias_desc[ghard]="Hard reset"
alias_desc[gcmundo]="Undo last commit (soft)"
alias_desc[grestore]="Restore file"
alias_desc[grestoreall]="Restore all files"
alias_desc[guns]="Unstage file"
alias_desc[gunsa]="Unstage all files"
alias_desc[gsh]="Stash changes"
alias_desc[gshapply]="Apply stash"
alias_desc[gshpop]="Pop stash"
alias_desc[gshls]="List stashes"
alias_desc[gshcl]="Clear all stashes"
alias_desc[gb]="List branches"
alias_desc[gbr]="List remote branches"
alias_desc[gba]="List all branches"
alias_desc[gco]="Checkout branch"
alias_desc[gcb]="Create & checkout branch"
alias_desc[gcl]="Clone repository"
alias_desc[gdf]="Diff changes"
alias_desc[gdfc]="Diff staged changes"
alias_desc[gsta]="Short status"
alias_desc[gcount]="Count commits per author"
alias_desc[gfixup]="Create fixup commit"
alias_desc[gsquash]="Interactive autosquash rebase"
alias_desc[gtag]="List tags"
alias_desc[gtags]="List tags (pattern)"
alias_desc[gshow]="Show commit details"
alias_desc[gfetch]="Fetch remote"
alias_desc[gfetchall]="Fetch all remotes"
alias_desc[gmerge]="Merge branch"
alias_desc[gundo]="Undo last commit (mixed)"
```
> ⚠️ **Warning:** If you add the function zle-line-pre-redraw to your .zshrc the terminal behaves differently. If the function is active and you paste a command in the terminal and tried to move your cursor, the characters would get deleted. Hence there are additional functions and keybindingsvto activate and deactivate the function. Scroll down to read more about them.

### Function to show alias hints on the right side
```bash
function zle-line-pre-redraw() {
  if [[ "$git_hint_active" != true ]]; then
    return
  fi
  local cmd="${BUFFER%% *}"
  local hint="${alias_desc[$cmd]}"
  local len=${#BUFFER}
  local spaces=8
  local hint_space=40   # max width of hint

  print -Pn "\e7"   # Save cursor

  if [[ -n "$hint" ]]; then
    # Move cursor after typed text + spaces
    printf "%*s" $((len + spaces)) ""
    # Print hint
    # print -Pn "%F{yellow}$hint%f"
    print -Pn "\e[38;2;21;27;35m$hint\e[0m"
  else
    # Clear previous hint if no match
    printf "%*s" $((len + spaces + hint_space)) ""
  fi

  print -Pn "\e8"   # Restore cursor
}
```

### Activate the hint system
```bash
git_hint_start() {
  # zle -N zle-line-pre-redraw
  zle -N zle-line-pre-redraw
  echo "Git hint system activated \n"
}
```

### Deactivate the hint system
```bash
git_hint_stop() {
  zle -D zle-line-pre-redraw
  echo "Git hint system deactivated"
}
```

### Automatically start if in a git repo
```bash
if [ -d .git ]; then git_hint_start; fi
```

### Toggle function
```bash
function git_hint_toggle() {
  if [[ "$git_hint_active" == true ]]; then
    git_hint_active=false
    zle -D zle-line-pre-redraw
    print -Pn "%F{yellow}Git hints deactivated%f\n"
    zle reset-prompt  # safely redraw prompt
    
  else
    git_hint_active=true
    zle -N zle-line-pre-redraw zle-line-pre-redraw
    print -Pn "%F{green}Git hints activated%f\n"
    zle reset-prompt  # safely redraw prompt
  fi
}
```
### Bind toggle to Ctrl+Option+G
```bash
zle -N git_hint_toggle
bindkey '\e^G' git_hint_toggle # Ctrl+Option+G
```
<!---
MayurShikhare/MayurShikhare is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
