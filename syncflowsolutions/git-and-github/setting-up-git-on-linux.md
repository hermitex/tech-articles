# How to Set up Git with SSH keys on Linux System Correctly

Setting up Git on a Linux OS is a relatively straightforward process. The following steps will guide you through the setup process:

1. Install Git: The first step is to install Git on your Linux OS. This can be done using the package manager of your choice, such as apt-get, yum, or dnf. For example, on Ubuntu you can use the following command to install Git:

```bash
sudo apt-get install git
```

2. Configure Git: Once Git is installed, you will need to configure it with your name and email address. This can be done using the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

3. Generate SSH Keys: SSH keys are used to authenticate your computer when connecting to remote Git repositories. To generate SSH keys, you can use the following command:

```bash
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

4. Add SSH Keys to the SSH Agent: Once you have generated your SSH keys, you will need to add them to the SSH agent. This can be done using the following command:

```bash
ssh-add ~/.ssh/id_rsa
```

5. Add SSH Keys to GitHub: Finally, you will need to add your SSH keys to your GitHub account. This can be done by going to the “Settings” page on your GitHub account and clicking on “SSH and GPG keys”. From there, you can click on “New SSH key” and paste in your public key.

For more information on setting up Git on a Linux OS, please see the following links:

- <https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-18-04>
- <https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent>
- <https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account>
