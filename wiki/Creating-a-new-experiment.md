Once you have an experiment ready that you'd like to run in the lab, it's best to put it under version control.

1. Create a git repo on your local computer.

```bash
cd /path/to/my/experiment
git init .
git add .
git commit -m "First version of the experiment"
```

2. Create a git repo on GitHub.

- Go to GitHub.com
- Click the "+" to create a new repository.
- Set the owner to "lupyanlab" and give it a name.

*Note:* Don't check the box for Initializing the repo with a README if you already created the repo on your local computer.

3. Point your local git repo to the GitHub endpoint

```bash
git remote add origin https://github.com/lupyanlab/name-of-my-repo.git
git push -u origin master
```

4. Install the experiment on the lab computers.

```bash
cd ~/Dropbox/LupyanExps
git clone https://github.com/lupyanlab/name-of-my-repo.git
```
