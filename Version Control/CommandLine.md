# Command Line

The aim of this guide is to get you familiar with the command line, in particular how it helps when SSHing into servers and with Git version control.

A server with an SSH daemon running on will allow you to be able to login and access the command line of that server (e.g. in order to pull stuff down via Git).

## Basics

Below are some basics commands and what they do, such as basic file management. Be especially careful when deleting files. 

|Command|Action|
|---|---|
|ls|List contents of a directory.|
|ls -la|Long listing with hidden files.|
|cd [folder]|Change to folder.|
|cd [folder]/[subfolder]|Change to subfolder.|
|cd ../|Change to root directory.|
|mv [from] [to]|Move file/folder.|
|cp [from] [to]|Copy a single file.|
|cp -r [from] [to]|Copy files/folders recursively.|
|Tilde (~)|Your home directory, (e.g. cd ~ will take you to your home directory).|
|/|Root directory of your computer.|
|./|Current directory.|
|../|Parent directory.|
|ssh [user]@[server]|SSH into server|
|ssh-keygen|Generate SSH key.|
|nano [file]|Edit/create [file] in nano.|
|vi [file]|Edit/create [file] in vi.|
|touch [file]|Create an empty file named [file].|
|rm [folder/file]|Delete [folder/file], **no confirmation/undo**!|
|rm -rf [folder/file]|Delete [folder/file] recursively by force, **no confirmation/undo**! **VERY DANGEROUS**|

## SSH Keys

SSH keys provide a more secure way of logging in than usernames or passwords, it is also more convienient. They work by you sharing a public key and keeping your private key secret. Your public key can be used to encrypt data which only your private key can decrypt. The server uses your public key to create cryptographic challenge which your computer must respond correctly to in order to gain access (challenge-response authentication).

1. Firstly let's generate a private and public key:
> Run **ssh-keygen** and confirm all options; your private key will be in **~/.ssh/id_rsa** and your public key will be in **~/.ssh/id_rsa.pub**. Share your public key, **never share your private key**.
2. To copy your key to your clipboard, simply run:
> pbcopy < ~/.ssh/id_rsa.pub
3. Add your key to BitBucket by doing the following:
> Go to Manage Accout > SSH Keys > Add Keys > Paste in key and click Add key.
4. Testing it:
> Run: **ssh -T git@bitbucket.org**, the first line of the message should be "logged in as [your username]."

## SSH into a server

1. Enable SSH access on the server by doing the following:
> Login via plesk, click Web Hosting Access; alongside **Access to the server over SSH** select **/bin/bash**.
2. Create a .ssh/config file with your config, as described in it's subsection below.
3. Add your keys:
> Run **ssh-add -K** (-k adds them to your keychain so you don't need to run ssh-add on each terminal session).
4. SSH into the server, the first time you will be asked for your password.
5. Using nano add your public key to the end of the .ssh/authorized_keys2 file.
6. Exit and relogin and you should not be asked for your password.

### .ssh/config file
Each server config in your SSH directory resembles something like this, add extra servers  to the bottom of the file each time. **ForwardAgent yes** allows you to access GitHub/BitBucket from the server you  ssh into.
```
Host [shorthand name]
    HostName [server IP address]
    User[server username]
    ForwardAgent yes
```

## Git via the command line

Whilst Git from an operational perspective will be covered in it's own training session; here's a mini-cheatsheet for the Git command line.

|Command|Action|
|---|---|
|git --help|List all git options.|
|git init|Initialise a git repository.|
|git add [file]|Add a file to git's staging set-up.|
|git add -A|Add all files and remove files that have been removed.|
|git commit -m "[message]"|Make a commit in git.|
|git push origin [branch]|Git push a branch up to BitBucket (origin).|
|git checkout [branch]|Checkout a branch that already exists in Git.|
|git checkout -b [branch]|Create and checkout a branch in Git.|
|git branch -d [branch]|Delete a branch in git.|
|git push origin :[branch]|Delete a branch on remote.|
|git status|List files changed that need to be added for committed.|
|git merge [branch]|Merge a branch into your active branch|


### Pulling changes via Git

After you SSH into the server you want to pull to, firstly you can clone a repository if you run a Git clone to the URL specified in BitBucket. In the example below we will clone it into a folder called httpdocs:

```
git clone git@bitbucket.org:creare/[repository].git ./httpdocs
git checkout staging
```

To redownload a repository you have already cloned in git, use the following commands:

```
git fetch --all
git reset --hard origin/master
```
