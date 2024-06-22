## Generating a new SSH key

You can generate a new SSH key on your local machine. After you generate the key,
you can add the public key to your account on GitHub.com to enable authentication for Git operations over SSH.

* First method using `RSA` algorithm, in your terminal type the following:
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com OR anything"
```

* Second method using `Ed25519` algorithm:
```
$ ssh-keygen -t ed25519 -C "your_email@example.com OR anything"
```

## First scenario, let's go with `RSA` algorithm and doing it in the easy way:
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com OR anything"
```
1. This creates a new SSH key, using the provided email/or/anything as a label.
```
> Generating public/private rsa key pair.
> Enter a file in which to save the key (/home/YourName/.ssh/id_rsa): [hit Enter key]
```
When it asks you to `Enter file in which to save the key`, it's asking you to name the key.
If you leave it blank and hit enter, it will use the default name of `id_rsa`.

2. Next, When it asks you to create a passphrase (it's a password), leave it blank and hit enter or set it
```
> Enter passphrase (empty for no passphrase): [hit enter]
```
Done, now if you list your `.ssh` directory you'll see something like this:
```
~ $ tree .ssh

.ssh
├── id_rsa
└── id_rsa.pub
```

3. Now, let's add the public key `id_rsa.pub` to your account on GitHub.com:  
First of all copy the content of `id_rsa.pub` file, from your terminal, use `cat` command to list `id_rsa.pub` content and then copy the output
```
$ cd ~/.ssh
ssh $ cat id_rsa.pub
```

then, go to your Github [Settings](https://github.com/settings/profile) then find the option for [SSH and GPG keys](https://github.com/settings/keys).  
From this page click the button `New SSH key`, now you see a page with the following fields:

`Title`
```
[title can be anything, for example: my fris ssh ]
```
`Key type`
```
[Leave default: Authentication Key]
```
`Key`
```
[paste your public key her ]
```

4. Let's test our SSH:
From your terminal type the following: 
```
$ ssh -T git@github.com
> Hi "your_email@example.com OR something else"! You've successfully autyenticated, but GitHub does not provide shell access.
```
Congratulation, now you can access your on GitHub.com via [SSH](https://en.wikipedia.org/wiki/Secure_Shell) to do all [Git](https://www.git-scm.com) operations.

But, you can't push yet if your `Origin remote` are still using `HTTPS URL` ,
you need to convert any existing `origin remote` into `SSH` one it's simple to do so,

### Change Existing Origin Remote to SSH:
`GitHub` project will have an `HTTPS URL` :
```
https://github.com/<Username>/<Project>.git
```

And the `SSH` one have:
```
git@github.com:<Username>/<Project>.git
```

- Now to convert existing Origin remote `HTTPS URL` to `SSH` do the following:
```
$ git remote set-url origin git@github.com:<Username>/<Project>.git
```

Example:
```
.dotfiles $ git remote -v

> origin  https://github.com/codex0x09/.dotfiles.git (fetch)
> origin  https://github.com/codex0x09/.dotfiles.git (push)

.dotfiles $ git remote set-url origin git@github.com:codex0x09/.dotfiles.git

.dotfiles $ git remote -v

> origin  git@github.com:codex0x09/.dotfiles.git (fetch)
> origin  git@github.com:codex0x09/.dotfiles.git (push)
```
For the next time you create new repo use `SSH` link.
