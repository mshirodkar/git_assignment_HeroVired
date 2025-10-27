# git_assignment_HeroVired
Practice Assignment : Git &amp;amp, Github
git config --global user.name "Mahesh Shirodkar"
git config --global user.email "Mahesh.mshirodkar@gmail.com"
git clone https://github.com/mshirodkar/git_assignment_HeroVired.git
git checkout -b dev

Create a file: calculator.py

Add and commit:
git add .
git commit -m "Initial commit with basic calculator functions"
git push origin dev

Merge dev → main (Version 1 Release)
git checkout main
git merge dev
git tag -a v1.0 -m "Release version 1 - CalculatorPlus basic functions"
git push origin main --tags


Add Collaborator
Go to GitHub → Repository → Settings → Collaborators
Add any classmate’s GitHub ID.

Create Feature Branch for Square Root
git checkout dev
git checkout -b feature/sqrt

Implement the square_root() method:
def square_root(self, x):
    return math.sqrt(x)

Commit & push:
git add .
git commit -m "Added square root feature"
git push origin feature/sqrt

Simulate Bug Fix on dev Branch
A bug in divide() — modify:
def divide(self, a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b

Commit & push fix:
git checkout dev
# apply fix
git add .
git commit -m "Fix divide by zero bug"
git push origin dev

Keep feature branch up-to-date:
git checkout feature/sqrt
git pull origin dev
# Resolve conflicts if any
git push origin feature/sqrt


Create Pull Request (PR):
Open GitHub
PR from feature/sqrt → main
Request code review from your collaborator.

After approval:
# Merge PR in GitHub UI or:
git checkout dev
git merge feature/sqrt
git push origin dev

Final Merge to Main and Create Version 2
git checkout main
git merge dev
git tag -a v2.0 -m "Release version 2 - Square root feature + divide bug fix"
git push origin main --tags

Q2: Git LFS Integration for Large Files
git checkout -b lfs

Install and Configure Git LFS
git lfs install
git lfs track "*.zip"  # example pattern
git add .gitattributes

Add a large file (>200MB):
cp C:\Users\HP\Downloads\VirtualBox-7.2.2-170484-Win .
git add VirtualBox-7.2.2-170484-Win.zip
git commit -m "Add large binary file with Git LFS tracking"
git push origin lfs


Clone the repo on another machine and verify:

Q3: Geometry Calculator with Git Stash Workflow
git checkout -b geometry-calculator

Add geometry_calculator.py:
Commit base:
git add .
git commit -m "Base geometry calculator file"

Circle Area Feature with Git Stash
git checkout -b feature/circle-area
# Add partial code
git stash save "Incomplete circle area feature"
git status  # should be clean

Rectangle Area Feature
git checkout -b feature/rectangle-area
# Add partial code
git stash save "Incomplete rectangle area feature"
git status

Complete Circle Area Feature
git checkout feature/circle-area
git stash pop
# Complete the code and test
git add .
git commit -m "Complete circle area feature"
git push origin feature/circle-area

Complete Rectangle Area Feature
git checkout feature/rectangle-area
git stash pop
# Complete the code and test
git add .
git commit -m "Complete rectangle area feature"
git push origin feature/rectangle-area
