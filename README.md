# Chive
Too many people on the hive machines again? No worries!
Chive helps you choose a hive machine with the least number of people on it and automatically logs you in.

## Installation
If you already have your public key on the hive then you're all set!
If you don't know have one or don't know what it is follow the the steps below.

1. Generate a public/private key pair. If you already have one you can skip to step 2.
`USER` and `MACHINE` should be your local username and machine.
For convenience sake you can simply keep pressing enter and take the defaults
```
$ ssh-keygen -t ed25519 # Example output below
Generating public/private ed25519 key pair.
Enter file in which to save the key (/USER/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /USER/.ssh/id_ed25519.
Your public key has been saved in /USER/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:5WSfAsAMqe9yEZZleRM/0xnHiqfc8CuVGLsOmn7CHY4 USER@MACHINE
The key's randomart image is:
+--[ED25519 256]--+
|    .=....  ...  |
|    . *.o. . +.  |
|   . + ...B.o.   |
|  . +    *++o.   |
|   o .  S.oXo.   |
|    o   . =.=    |
|   . o +.. o .   |
|  . o Eo+.o .    |
|   o .+o ...     |
+----[SHA256]-----+
```
2. Copy your public key to the hive.
Replace `USERNAME` and `HIVE_X` with your instructional account username and any online hive machine (e.g. `hive12`, my favorite :heart:).
```
$ ssh-copy-id USERNAME@HIVE_X.cs.berkeley.edu
```
Alternatively you can do
```
$ cat ~/.ssh/id_rsa.pub | ssh USERNAME@HIVE_X.cs.berkeley.edu "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >>  ~/.ssh/authorized_keys"
```
Now you're all set!

## Usage
By default, chive will use your local username and `~/.ssh/id_rsa` for your private key.
Since I don't think anyone has the same local username as their instructional account,
you should tell chive to use your instructional account username instead.
```
$ chive -u USERNAME
```
`chive -h` for help and additonal options.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Inspired By
- [Choose Hive](https://github.com/nherson/choose-hive)
- My CS61C professor [Nicholas Weaver](https://github.com/nherson/choose-hive)
- Massive amounts of people on the hive

