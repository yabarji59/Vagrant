## Command line instructions
***You can upload existing files from your computer using the instructions below.***

#### Git global setup
```
git config --global user.name "Yassen A"
git config --global user.email "yabarji@yahoo.fr"
```
#### Create a new repository
```
git clone git@gitlab.com:yabarji1/yassen_project.git
cd yassen_project
git switch -c main
touch README.md
git add README.md
git commit -m "add README"
git push -u origin main
```

#### Push an existing folder
```
cd existing_folder
git init --initial-branch=main
git remote add origin git@gitlab.com:yabarji1/yassen_project.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

#### Push an existing Git repository
```
cd existing_repo
git remote rename origin old-origin
git remote add origin git@gitlab.com:yabarji1/yassen_project.git
git push -u origin --all
git push -u origin --tags
```