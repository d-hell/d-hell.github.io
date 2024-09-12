Add an ssh key to Github:

1. Paste the text below, replacing the email used in the example with your GitHub email address.
```terminal
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

This creates a new SSH key, using the provided email as a label.

```
> Generating public/private ALGORITHM key pair.
```

When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ALGORITHM with your custom key name.

```
> Enter a file in which to save the key (/home/YOU/.ssh/id_ALGORITHM):[Press enter]
```

2. At the prompt, type a secure passphrase.

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

3. To add your SSH key to the ssh-agent, start ssh-agent in the background.

```
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```

Depending on your environment, you may need to use a different command. For example, you may need to use root access by running `sudo -s -H` before starting the ssh-agent, or you may need to use `exec ssh-agent bash` or `exec ssh-agent zsh` to run the ssh-agent.

4. Add your SSH private key to the ssh-agent.

If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

```
ssh-add ~/.ssh/id_rsa
Enter passphrase for /home/<user>/.ssh/id_rsa: 
Identity added: /home/squid/.ssh/id_rsa (<email>)
```

5. Copy the public key information.

```
$ cat ~/.ssh/id_rsa.pub
# Then select and copy the contents of the rsa.pub file
# displayed in the terminal to your clipboard
```

6. Enter into the Github settings SSH and GPG Keys page.

7. Test your ssh key.

```
ssh -T git@github.com
```

You may need to type "yes" to approve a connection. If your ssh key is properly set up, you will see the following message:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```


