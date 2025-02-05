# Lathund för git

Setup:

```bash
git config --global user.name Namn
git config --global user.email email@domain.com
```

## Grundläggande

Kommando | Beskrivning
--------------- | -------------------------
`git init` | Skapa repository
`git add .` | Lägg till alla filer (.) från aktuell katalog
`git add -p` | Fråga om man vill lägga till del för del för filerna
`git commit -m "meddelande"` | Committa med meddelande

## Branch

Kommando | Beskrivning
--------------- | -------------------------
`git branch` | Lista branches
`git checkout branch1` | Checka ut branch
`git branch nybranch` | Skapa ny branch
`git branch --merged` | Se vilka föräldrar som aktuell branch har
`git branch -d gammalbranch` | Ta bort branch
`git checkout master` & `git merge branch1` | Merga ihop branch1 med master
`git log --graph --oneline --all --decorate` | Visar grafiskt träd över alla branches och commits

## Diff/log

Kommando | Beskrivning
--------------- | -------------------------
`git diff branch1..branch2` | Jämföra förändringar mellan branches
`git diff --name-only SHA1 SHA2` | Visa filer som ändrats mellan två commits
`git diff --name-only HEAD~10 HEAD~5` | Visa filer som ändrats mellan 10:e commiten och 5:e commiten
`git show 7ed4266cf` | Visa ändringar i commit 
`git log --oneline` | Visa logg över commit
`git log --grep=hej` | Sök efter "hej" i loggen

## Stash

Kommando | Beskrivning
-------------------------- | --------------------
`git stash save "meddelande"` | Spara tillfälligt i stashen
`git stash list` | Visa stashen
`git stash show -p stash@{0}` | Visa ändringarna i stash 0 (precis som diff)
`git stash pop stash@{0}` | Hämta det som finns i stashen och lägg i working directory (använd "apply" i stället för "pop" om stashen ska finnas kvar)
`git stash drop stash@{0}` | Ta bort objekt från stashen
`git stash clear` | Ta bort allt från stashen

## Återställa

Kommando | Beskrivning
-------------------------- | --------------------
`git checkout -- .` | Återställ working directory till repository
`git fetch --all` & `git reset --hard origin/master` | Tvinga git att skriva över lokala ändringar, hämta med pull (alla ändringar i working directory tas bort!)

## Länkar

- [Bitbucket: Set up an SSH key](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/)
- [Git Cheat Sheet](https://www.git-tower.com/blog/git-cheat-sheet/)
- [YouTube: Introduction to Git with Scott Chacon of GitHub](https://www.youtube.com/watch?v=ZDR433b0HJY)
