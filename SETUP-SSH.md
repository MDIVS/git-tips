### [Go back to git tips](./README.md)

# Add a GitHub SSH Key on Windows
All the commands here were tested on Windows 11 and I have no idea if they work on Windows 10.

## 1. SSH Files
On this step you are going to create the private and public ssh keys using the BASH (it usually comes with git when you download it).

Move to the standard ssh webpage (make sure that the ".ssh" folder exists, you can create it if needed):

    cd ~/.ssh/

Create the ssh private (mdivs-github) and public key (mdivs-github.pub):

    ssh-keygen -t rsa -b 4096 -C "maiconoficialbr@gmail.com"

When asked, give a name to the ssh file. For this tutorial, I'll give the name `mdivs-github`. You will also be asked to input a password of your preference.

Start the ssh-agent with eval:

    eval $(ssh-agent -s)

Add the private key (mdivs-github) to the agent with ssh-add.
    
    ssh-add ~/.ssh/mdivs-github

Copy the public key (mdivs-github.pub) to your clipboard to add it to your Git service (GitHub, GitLab, etc.):

    clip < ~/.ssh/mdivs-github.pub

## 2. Config files
Create a `config` (without any extension) empty file inside the `~/.ssh` folder with the following content:
> ! Note that I'm using my personal key name "mdivs-github" as example.

    # GITHUB
    Host mdivs-github
        HostName github.com
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/mdivs-github

Or you can simply use the below command:

    echo "# GITHUB`nHost mdivs-github`n    HostName github.com`n    PreferredAuthentications publickey`n    IdentityFile ~/.ssh/mdivs-github" > config