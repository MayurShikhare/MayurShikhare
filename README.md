- 👋 Hi, I’m @MayurShikhare
- 👀 Interested in technologies and design in general.
- 🌱 currently building AURA - your financial intelligence.
- 📫 you can reach me via https://mayur-shikhare.netlify.app/

View the full `.zshrc` file [here](https://github.com/MayurShikhare/MayurShikhare/blob/main/.zshcrc)

# My Zsh Configuration

## Git Aliases - some of the most used Git aliases

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



## Descriptions

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

<!---
MayurShikhare/MayurShikhare is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
