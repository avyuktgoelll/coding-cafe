# Lab 4 Notes

Q) Question 1
`--global` stores the setting for my user account on this computer, so every repository I create uses the same name and email. Without it, Git saves the setting only in the current repository, and the command would fail outside a repo.

Q) Question 2
`ls -a` showed hidden items that plain `ls` doesn't, and the important new one is `.git`. It stores the repository's whole history and settings (commits, branches, config). It is what turns the folder into a Git repository.

Q) Question 3
Git offered to track 3 items: `.DS_Store`, `lab3.ipynb` and the `week-02/` folder. `.DS_Store` is a hidden macOS system file that I did not write.

Q) Question 4
`.DS_Store` disappeared from the untracked list because `.gitignore` tells Git to ignore it. In its place, `.gitignore` itself appeared as a new untracked file.

Q) Question 5
`.gitignore` should be committed, not ignored. It is part of the project, and committing it means anyone who clones the repo gets the same ignore rules.

Q) Question 6
`README.md` moved from the "Untracked files" section to the "Changes to be committed" section. In the three-places model, `git add` moved it from the working directory to the staging area. It was queued for the next commit but not yet saved in the repository.

Q) Question 7
Git printed `[main (root-commit) 66ddf1f] Lab work so far` and `6 files changed, 565 insertions(+)`. The six files were `.gitignore`, `README.md`, `lab3.ipynb`, `week-02/lab01-log.txt`, `week-02/notes.md` and `week-02/notes.md.save`.

Q) Question 8
The first seven characters of my commit are `66ddf1f`. This is the short form of the commit's unique ID (hash), used to refer to that exact commit, for example to inspect it or go back to it.

Q) Question 9
The loop is: edit the files, check with `git status`, stage with `git add`, then save with `git commit` (and confirm with `git log --oneline`).
Q) Question 10
README.md gets a special name and location because GitHub looks for a file called README in the top folder and shows it as the front page of the repository. That makes it the project's shop window, so anyone who visits sees what the project is and who made it before opening anything else.

Q) Question 11
gh auth login logged me in to GitHub through the browser and saved an access token on my computer. It also set up Git to use that token, so pushes over HTTPS authenticate automatically and never ask for a password.

Q) Question 12
The front page shows my README.md rendered as formatted text: the Coding Café heading, my name and roll number, and the Contents list. GitHub shows the README there automatically because it treats it as the project's front page.

Q) Question 13
No. Pushing only copies my commits to GitHub. My local history is the same as before, and the only visible difference is the origin/main label that now appears next to the latest commit.

Q) Question 14
A private repository does exist on GitHub, but only people I give access to (me and the TAs) can see it. A repository that doesn't exist on GitHub means there is no online copy at all, only the one on my laptop. So private is about who can see it, not whether it exists.
