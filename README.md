# Setting Up a Git Project on Forge with SSH

## 1. Generate SSH Key Pair

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
This command generates an SSH key pair. Press Enter to accept the default file location (~/.ssh/id_rsa) and set an optional passphrase for added security.

## 2. Add SSH Key to Forge Account
- Display the public key:
```bash
cat ~/.ssh/id_rsa.pub
```
Copy the public key.
- Log in to your Forge account.
- Navigate to account or security settings.
- Find the option to add a new SSH key.
- Paste the copied public key and save the changes.

## 3. Create a Project and Repository on Forge

- Go to the Forge website.
- Create a new project and repository with the desired name.
## 4. Configure Local Git Repository

- Open a terminal.
- Navigate to your project directory:
```bash
cd /path/to/your/project
```
- Initialize a new Git repository:
```bash
git init
```
- Add your Forge repository as the remote with SSH URL:
```bash
git remote add origin git@forge.ird.fr:espace-dev/personnels/jiang/demo_git.git
```
## 5. Create and Push Initial Commit

- Create and switch to the "main" branch:
```bash
git checkout -b main
```
- Create a README or your initial project files:
```bash
touch README.md
```
- Add and commit the changes:
```bash
git add README.md
git commit -m "Initial commit"
```
- Push the changes to the remote repository:
```bash
git push -u origin main
```
## 6. Verify Remote Configuration

- Ensure that the remote URL is using SSH:
```bash
git remote -v
```
- Verify that the fetch and push URLs are in the SSH format.
- If you want to add another remote for GitHub, here's how you can proceed:
```bash
git remote add github https://github.com/votre_utilisateur/votre_projet.git
git push -u github main
# Push changes to both GitHub and Forge remotes
git push --all

```