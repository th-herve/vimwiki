# Git configuration

In the email setting, check the two box to keep email address secret.


## 1. Configure git in terminal

1. Enter your information (with the `""`).
>git config --global user.name "Your Name"
>git config --global user.email "yourname@example.com"
 
>> `!!`be sure to include the quote`""`

2. Optional: change the default branch name to main
>git config --global init.defaultBranch main

3. Set up colorful output
>git config --global color.ui auto

4. Optional: set the default branch reconciliation behavior
>git config --global pull.rebase false

## 2. Set up ssh

1. Check if a ssh key already exits
> ls ~/.ssh/id_ed25519.pub

2. If not create one (capital C, `no` quotes ~~""~~)
> ssh-keygen -t ed25519 -C yourmail@example.com

When prompted for a location to save the key, press `enter`
It is best to set a passphrase but not required.
 
>> `!!` Do `not` include quote ~~""~~

## 3. Link the ssh key to your Github account

1. Go to `settings` -> `SSH and GPG keys` -> `New SSH Key`(green button top right)
2. In therminal, copy the ssh key with: (`!!` include the `.epub` `!!`, should begin with ssh-ed25519, and finish with your email)
    1. cat ~/.ssh/id_ed25519.pub
3. Past the key in the key field
4. Select type as `Authentication Key`
5. Click `Add SSH key`
