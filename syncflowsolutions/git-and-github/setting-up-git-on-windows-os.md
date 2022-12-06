# How to Set up Git with SSH keys on Windows OS Correctly

Setting up Git on Windows can be a bit tricky, but with the right steps and resources, it can be done quickly and easily.

First, you will need to download and install Git for Windows. You can find the download link [here](https://git-scm.com/download/win). Once you have downloaded the installer, run it and follow the instructions to install Git.

Once Git is installed, you will need to configure it. To do this, open a command prompt window and type in the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

This will set your username and email address for Git.

Next, you will need to generate an SSH key. SSH keys are used to authenticate your computer when connecting to remote repositories. To generate an SSH key, open a command prompt window and type in the following command:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

This will generate an SSH key pair. You will be prompted to enter a passphrase, which is used to protect your private key. Once the key is generated, you will need to add it to your remote repository. To do this, open a command prompt window and type in the following command:

```bash
ssh-add ~/.ssh/id_rsa
```

This will add your SSH key to the remote repository. You can now use Git with your remote repository.

For more information on setting up Git on Windows, you can refer to the official documentation [here](https://git-scm.com/book/en/v2/Git-on-Windows-Setting-Up-a-Development-Environment).
