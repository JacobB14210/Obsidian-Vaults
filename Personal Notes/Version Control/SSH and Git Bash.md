# Setup SSH key
- Do all the SSH setup in Git Bash
- school and personal is interchangeable
- Generate SSH key
```bash
ssh-keygen -t rsa -b 4096 -C "your-personal-email@example.com" -f ~/.ssh/id_rsa_personal
```

- Start SSH agent
```bash
eval "$(ssh-agent -s)"
```

- Add SSH keys to agent
```bash
ssh-add ~/.ssh/id_rsa_personal
# Check if added
ssh-add -l
```

- Add this SSH key to GitHub in settings
```bash
cat ~/.ssh/id_rsa_personal.pub
```

- Edit SSH config
```bash
cat ~/.ssh/id_rsa_personal.pub

# Config file
# Personal GitHub account
Host github-personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_personal
```

# Clone Repository with SSH Key
```Command
git clone git@github-personal:JacobB14210/personal-repo.git
git clone git@github-school:JacobBarrios/school-repo.git
```
# Link Local to Remote Repo
```Command
git remote add origin git@github-personal:JacobB14210/REPO.git
git remote add origin git@github-school:JacobBarrios/REPO.git
```

# Set Git Identity For Each Repo
```Command
cd personal-repo
git config user.name "JacobB14210"
git config user.email "jake.m.barrios@gmail.com"
```

# SSH Keys File Locations
- Users/jakem/.ssh

- Use Git Bash
```
cd ~/.ssh/
dir
```