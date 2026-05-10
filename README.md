Complete Detailed Guide
Doc-as-Code using Git + README + MkDocs + Jenkins
For Multiple Git Repositories

This guide explains how to build a centralized documentation portal using:

Git
GitHub
MkDocs
Jenkins
Multiple repositories containing README.md

The goal is:

✅ Automatically collect README files from multiple repositories
✅ Display them in one organized static documentation website
✅ Create sidebar navigation tree
✅ Automatically update website when developers modify README files
✅ Use only FREE tools/resources

📚 TABLE OF CONTENTS
What is Doc-as-Code
Final Architecture
Install Required Tools
Create Central Documentation Project
Configure MkDocs
Manage Multiple Repositories
Create Automation Script
Create Sidebar Navigation
Run Website Locally
Setup GitHub
Configure Jenkins
Automate Documentation Updates
Configure GitHub Webhooks
Deploy Static Website
Daily Workflow
Common Errors and Fixes
Best Practices
Future Improvements
1. WHAT IS DOC-AS-CODE

Doc-as-Code means:

Documentation is managed like source code

Instead of:

Word documents
Shared folders
Manual updates

You use:

Markdown files (README.md)
Git repositories
CI/CD automation
Static documentation websites
2. FINAL ARCHITECTURE
Developer updates README.md
              ↓
Pushes code to GitHub
              ↓
GitHub webhook triggers Jenkins
              ↓
Jenkins pulls latest repositories
              ↓
README files copied automatically
              ↓
MkDocs rebuilds website
              ↓
Static documentation site updated
3. INSTALL REQUIRED TOOLS
✅ STEP 1 — Install Homebrew (Mac)

Open Terminal.

Run:

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Verify:

brew --version
✅ STEP 2 — Install Git

Run:

brew install git

Verify:

git --version

Configure Git:

git config --global user.name "Your Name"

git config --global user.email "your-email@gmail.com"
