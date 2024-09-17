## Second scenario, with `RSA` algorithm and doing it in the Hard way:


## Example of `ssh-keygen -t rsa -b 4096 -C "codex0x09"`, you'll see something like this:

```log
> Enter a file in which to save the key (/home/codex/.ssh/id_rsa):  [I can leave it blank and accept the default name]
> Enter passphrase (empty for no passphrase):   [set password for your keys or leave it blank and hit enter]
```

* But, I unwant the default name `id_rsa` !!

```log
$ ssh-keygen -t rsa -b 4096 -C "codex0x09"
> Enter a file in which to save the key (/home/codex/.ssh/id_rsa): codex_at_git
> Enter passphrase (empty for no passphrase): 
```

```sh
~ $ tree .ssh

.ssh
├── codex_at_git
└── codex_at_git.pub
```

## How to Set, Reset, or even Change the passphrase:

```sh
# first, navigate to your [.ssh] dir or use absolute path as you wish,
# then do the following by choosing your private key, that you're using

~/.ssh $ ssh-keygen -p -f codex_at_git

# in case you want to Set the passphrase
Key has comment 'codex0x09'
Enter new passphrase (empty for no passphrase): [my_password] [Enter]
Enter same passphrase again: [my_password] [Enter]
Your identification has been saved with the new passphrase.

# in case you want to Reset the passphrase
Enter old passphrase: [my_password] [Enter]
Key has comment 'codex0x09'
Enter new passphrase (empty for no passphrase): [Enter]
Enter same passphrase again: [Enter]
Your identification has been saved with the new passphrase.

# in case you want to Change the passphrase
Enter old passphrase: [your_Old_password] [Enter]
Key has comment 'codex0x09'
Enter new passphrase (empty for no passphrase): [your_New_password] [Enter]
Enter same passphrase again: [your_New_password] [Enter]
Your identification has been saved with the new passphrase.

 ~/.ssh $ 
```

###  That's it. Take care `<(^.^)>`
