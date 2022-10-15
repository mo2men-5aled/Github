# Git & Github for Bignners

## SSH keys

in order to push something to github, you need to proof that you are the owner of the account, so you have to connect your computer to your github account, and you do that by creating a SSH key.

```
ssh-keygen -t rsa -b 4096 -C "your email"
```

- -t: type of key ---> rsa
- -b: size of key ---> 4096
- -C: comment ---> your email

if tried to see the sshkey file you have created type :

```
ls | grep <filename>
```

1- now you will find two files with the same name

- **sshkey file :** it iss you ssh key it is private and you should not share it with anyone you should keep it secure
- **sshkey.pub file :** it is the key that you are going to use to connect your computer to your github account the extension of this file is .pub that means that it is a public key it is okay if the other people see it.

2- now you have to add your sshkey to your github account

- go to github.com
- click on settings
- click on SSH and GPG keys
- click on new SSH key
- give it a title
- copy the content of the sshkey.pub file
- click on add SSH key
  now you are connected to your github account

3- after that you have to make sure that your local git CLI knows about the key you generated on the github account
use the command ssh-add <filename> to add that ssh key to the ssh-agent

```
ssh-add <filename>
```
