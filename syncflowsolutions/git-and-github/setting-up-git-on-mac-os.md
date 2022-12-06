# How to Set up Git with SSH keys on Mac OS Correctly

Setting up Git on Mac OS is a relatively straightforward process. The following steps will guide you through the setup process:

1. Download and install Git: The first step is to download and install the latest version of Git for Mac OS from the [official website](https://git-scm.com/download/mac).

2. Configure Git: After installing Git, you will need to configure it with your name and email address. This can be done by running the following commands in the terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

3. Generate SSH Keys: SSH keys are used to authenticate your computer when connecting to remote repositories. To generate an SSH key, run the following command in the terminal:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

This will generate a public and private key pair. The public key should be added to your remote repository, while the private key should be kept safe and secure.

4. Add SSH Key to SSH Agent: The SSH agent is a program that stores your SSH keys and allows you to use them without having to enter a password each time. To add your SSH key to the agent, run the following command in the terminal:

```bash
ssh-add -K ~/.ssh/id_rsa
```

This will add your SSH key to the agent and allow you to use it without having to enter a password.

5. Test Connection: To test that your SSH key is working correctly, run the following command in the terminal:

```bash
ssh -T git@github.com
```

If everything is working correctly, you should see a message that says “You’ve successfully authenticated, but GitHub does not provide shell access.”

And that’s it! You have now successfully set up Git on Mac OS. For more information, please refer to the official [documentation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
