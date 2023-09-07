---
layout: post
title: Setting up ssh keys for password-less connection.
date: 2019-08-07
title: "How to set up ssh-keys to connect to a remote machine without password"
---
I have done this so many times but without actually remembering how to do it properly. So here's my personal note on how to do it.
I took inspiration from the [Github guidelines](https://help.github.com/en/articles/about-ssh).

# Protocol

## Check for existing keys
Navigate to the `.ssh/`folder: `cd ~/.ssh/` and type `ls -al ./` to list possible public SSH keys.   
Public SSH keys should be named:
* `id_dsa.pub`
* `id_ecdsa.pub`
* `id_ed25519.pub`
* `id_rsa.pub`.

## Generate a new SSH keys
1. If you don't have a public key yet, open a Terminal window (Bash Shell).  
2. Type: `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` indicating an email adress.  
3. This creates a new ssh key, using the provided email as a label.  
4. When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location. `Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]`  
5. At the prompt, type a secure passphrase. I prefer not to have one as it saves quite some time when connecting regularly to the same remote machine. It will prompt you: `Enter passphrase (empty for no passphrase): [Type a passphrase]`. Type enter.

## Adding your SSH key to the ssh-agent.
1. Start the ssh-agent in the background. Type `eval "$(ssh-agent -s)"`.
2. Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file. Type `ssh-add -K ~/.ssh/id_rsa`.
3. Copy the SSH key to your clipboard: `pbcopy < ~/.ssh/id_rsa.pub`. If your SSH key file has a different name than the example code, modify the filename to match your current setup.

## Adding your SSH key to the remote.

### Github
Please refer to this manual: https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account

### Genseq
1. Login to genseq with your password. `ssh myusername@genseq-h0.science.uva.nl`.
2. Go to `~/.ssh/`
3. Open the `id_rsa.pub` file (or create a public key name using the same name as on your machine). Type: `nano id_rsa.pub`.
4. Copy-paste the public SSH key (stored in your clipboard).

### LISA cluster
Please refer to https://userinfo.surfsara.nl/systems/lisa/user-guide/connecting-and-transferring-data
