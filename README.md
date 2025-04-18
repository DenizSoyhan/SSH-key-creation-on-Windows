# How to add SSH key from Windows Computer
>There is a tool called **Git Bash** that comes with git installation. Open it.
<p align="center">
  <img src="https://github.com/user-attachments/assets/66be9f35-ca8c-469f-b85f-42d0113719d1" alt="gitBash">
</p>

## Step 1) Check if you already have SSH keys
> Type this in Git Bash:

```bash
ssh-keygen -t ed25519 -C "your-own-github-email@address.com"
```
>If it says 

```bash
ls: cannot access '/c/Users/UserName/.ssh': No such file or directory
```
Perfect! It means we will start fresh. So no worries.
If you already have keys just jump to the [Step 3](#step-3\)-see-our-key-pair)<br>

## Step 2) Create the SSH keys

> Type this in Git Bash:
> 
```bash
ssh-keygen -t ed25519 -C "your-own-github-email@address.com"
```
It will prompt you with something similar:
```bash
Enter file in which to save the key (/c/Users/UserName/.ssh/id_ed25519):
```
Press enter and it will create a directory on the specified location.
It will prompt you with:

```bash
 Enter passphrase (empty for no passphrase):
 Enter same passphrase again:
```
Just press enter. This is for extra security but it is secure as it is right now so we don't care.

If you see this you are done with this step:


<p align="center">
  <img src="https://github.com/user-attachments/assets/53d54c64-47e4-4b7c-b192-22fa76b839f5" alt="sshKeyCreationSuccess">
</p>

## Step 3) See our key pair
>Navigate to your **~/.ssh** directory with this command using git bash

```bash
cd ~/.ssh
```
>List the contents of the directory with:

```bash
ls
```
>It will look like this:

```bash
id_ed25519  id_ed25519.pub
```
This is a SSH key pair. You never ever share **id_ed25519** with anyone. But **id_ed25519.pub** is totally OK to share. Now lets see your public key with:
```bash
$ cat id_ed25519.pub
```
It will give you something like this:

```bash
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGVBfVc8LrfdDC0g1g+DeRm3NJqOHN/Q/DuLF1BGCI/I oguldenizsoyhan@gmail.com
```
## Step 4) Add SSH public key to github
>Open up github. Go to Setting -> SSH and GPA Keys. Press "New SSH key".

<p align="center">
  <img src="https://github.com/user-attachments/assets/ac3176c5-0cf8-47fc-bf43-eddb33efb5f6" alt="sshKeyCreationSuccess">
</p>

Add your public key that you got from privious step with a title like "myFirstKey".

## 5)Check the connection
In 1-3 minutes after you added your key to github you can check the connection from cmdwith:
```bash
ssh -T git@github.com
```
If you see this you are good to go!
```bash
Hi UserName! You've successfully authenticated, but GitHub does not provide shell access.
```


