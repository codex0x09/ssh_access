## Simple Intro:

You can generate a new SSH key on your local machine. After you generate the key,
you can add the public key to your account on GitHub to enable authentication for Git operations over SSH,
instead of using access Tokens, in which you'll use each time `user name` and `Access Token` (generated password via GitHub).
While using `SSH` we can easily do Git operations without each `push` doing `user name` and `complicated password`,
we can see this in the [Easy Way SSH](https://github.com/codex0x09/ssh_access/blob/master/easy_way.md).

`SSH` by default is secure, form its name `Secure Shell`, but we can make to become `Super Secure Shell`,
by adding another layer of security to the `SSH private key`, that is called `Passphrase`, it asks you to enter the `password`
each time you want to access your GitHub account to `push` or doing any changes to your account via the `SHELL`,
we can see this in the [Hard Way SSH](https://github.com/codex0x09/ssh_access/blob/master/hard_way.md).  
SSH is secure, but why we may need to add another layer of security ?  
Simply you may in public place, or for any reason you want to set a `Passphrase`(password) temporarily and then to remove it 
easily, you can do so by reading [Hard Way SSH](https://github.com/codex0x09/ssh_access/blob/master/hard_way.md).

## First Step [Easy Way SSH](https://github.com/codex0x09/ssh_access/blob/master/easy_way.md).

## Second Step [Hard Way SSH](https://github.com/codex0x09/ssh_access/blob/master/hard_way.md).

> [!NOTE]
> Please, keep reading the Unix/Linux manuals for more information/clarify.
> In both cases in this tutorial we going to work with `ssh-keygen` command to generate SSH KEY,
> you can simply from you terminal type `man ssh-keygen` then you can find good info
> about what `ssh-keygen` is, what all its `flags`(arguments) mean, and other topics related to it.
> you can find `manual pages` (Unix/Linux manuals) online too, and here some of them:

* For our tutorial:-  
 Linux: man7 [ssh-keygen(1)](https://man7.org/linux/man-pages/man1/ssh-keygen.1.html)  
 Linux: Linux man page [ssh-keygen(1)](https://linux.die.net/man/1/ssh-keygen)  
 Unix: freeBSD man [ssh-keygen(1)](https://man.freebsd.org/cgi/man.cgi?query=ssh-keygen&apropos=0&sektion=0&manpath=FreeBSD+14.1-RELEASE+and+Ports&arch=default&format=html)  

* In general:  
 The Linux man page maintainer: [man7](https://man7.org)  
 Easy to work with: [Linux man pages](https://linux.die.net/man/)  
 Easy to work with: [Unix / FreeBSD Manual Pages](https://man.freebsd.org/cgi/man.cgi)  
