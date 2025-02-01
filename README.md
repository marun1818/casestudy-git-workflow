# Initialize the Git Working Directory
mkdir casestudy-git-workflow
cd casestudy-git-workflow
ls

git init  # Initialize Git Repository

# Add and commit files to the main/master branch
touch master.txt
git add master.txt
git commit -m "Initial commit"

# Create and switch to develop branch
git checkout -b develop

touch develop.txt  # Add new file in develop branch
git add develop.txt
git commit -m "Develop files added in develop"

# Create feature branches from develop
git branch feature1
git branch feature2

# Switch to feature1 branch and add files
git checkout feature1
touch feature1.txt
git add feature1.txt
git commit -m "Feature1 files added in feature1"

# Switch to feature2 branch and add files
git checkout feature2
touch feature2.txt
git add feature2.txt
git commit -m "Feature2 files added in feature2"

# Merge feature branches into develop
git checkout develop
git merge feature1
git merge feature2

# Create and switch to release branch
git checkout -b release

git merge develop  # Merge all development changes into release

# Switch to main/master branch
git checkout master  # or main
git merge release  # Merge release into main/master

# Push to remote repository
git remote add origin https://github.com/marun1818/casestudy-git-workflow.git
git branch -M main
git push -u origin --all

# Monthly release cycle: Code from develop, feature branches, and release branch follows this workflow to deploy updates every 25th of the month.
