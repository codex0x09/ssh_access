### Second scenario, with `RSA` algorithm and doing it in the Hard way:

* *_Example: when you run `$ ssh-keygen -t rsa -b 4096 -C "codex0x09"`, you'll see something like this_*

```sh
> Enter a file in which to save the key (/home/codex/.ssh/id_rsa): [you can leave it blank to accept the default name]
> Enter passphrase (empty for no passphrase): [set password for your key or leave it blank and hit enter]
```

* *_But, what if you don't want the default name `id_rsa` !!?_*

```sh
# I'm going to set mine, you can do so
~ $ ssh-keygen -t rsa -b 4096 -C "codex0x09"
> Enter a file in which to save the key (/home/codex/.ssh/id_rsa): codex_at_git [Enter]
> Enter passphrase (empty for no passphrase): [Enter]
```

```sh
~ $ tree .ssh

.ssh
├── codex_at_git       # -- private key
└── codex_at_git.pub   # -- public key
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
```

####  That's it. Take care `<(^.^)>`
