# Chive
Too many people on the hive machines again? No worries!  
Chive helps you choose a hive machine with the least number of people on it and automatically logs you in.

## Installation
If you already have your public key on the hive then you're all set!  
If you don't have one or don't know what it is, that's okay.
Just follow the the steps below.

**1. Generate a public/private key pair.** If you already have one you can skip to step 2.  
(NOTE: `USER` and `MACHINE` should be your local username and machine.
For convenience, you can simply keep pressing enter and use the defaults)
```
$ ssh-keygen -t ed25519 # Example output below
```
**2. Copy your public key to the hive.** Replace `USERNAME` and `HIVE_X` with your instructional account username and any online hive machine (e.g. `hive12`, my personal favorite :heart:).
```
$ ssh-copy-id USERNAME@HIVE_X.cs.berkeley.edu
```
Alternatively you can do
```
$ cat ~/.ssh/id_rsa.pub | ssh USERNAME@HIVE_X.cs.berkeley.edu "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >>  ~/.ssh/authorized_keys"
```
**3. Now you're all set!** :tada:

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
- Too many people on the hive at the same time

