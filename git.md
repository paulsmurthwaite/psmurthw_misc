## Linux Installation

### Update System

```bash
sudo apt update
sudo apt upgrade
```

### Install Git

```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
```
### Verify version

- Check for minimum version of 2.28:

```bash
git --version
```

## Configure Git and GitHub

### Configure a local Git user

```bash
git config --global user.name "Your Name"
git config --global user.email "yourname@example.com"
```

### Change the default branch for Git

```bash
git config --global init.defaultBranch main
```

### Enable colourful output with Git

```bash
git config --global color.ui auto
```

### Verify the output matches your name and email address

```bash
git config --get user.name
git config --get user.email
```

## Link local Git user to GitHub

### Check if an Ed25519 algorithm SSH key already installed

```bash
ls ~/.ssh/id_ed25519.pub
```

- If a message appears in the console containing the text “No such file or directory”, then you do not yet have an Ed25519 SSH key, and you will need to create one.

### Generate a SSH key

```bash
ssh-keygen -t ed25519 -C yourname@example.com
```

- When it prompts you for a location to save the generated key, press Enter.
- Next, it will ask you for a password; enter one if you wish, but it’s not required.

### Link Your SSH Key with GitHub

- In GitHub account:
1. click the profile picture in the top right corner
2. click Settings in the drop-down menu
3. on the left-hand side, click SSH and GPG keys
4. click the green button in the top right corner that says New SSH Key
5. name the key
6. leave this window open and complete the next step
7. copy your public SSH key per below

```bash
cat ~/.ssh/id_ed25519.pub
```

8. highlight and copy the output, which starts with ssh-ed25519 and ends with the email address
9. paste the key in the GitHub field
10. click Add SSH key

### Test the SSH Key

- Follow [this article](https://help.github.com/en/articles/testing-your-ssh-connection)
- Expected output: 
>Hi username! You’ve successfully authenticated, but GitHub does not provide shell access
