## Use
I will use different SSH keys for everything I access from each device. To do this, I need to name each SSH key differently - something that makes sense.

#### Linking
To link the SSH key to the domain it connects:
1. Open the SSH config file
```shell
vim ~/.ssh/config

# If doing it for the first time the file may not exist so you need to copy the sample one accross
cp /etc/ssh/ssh_config ~/.ssh/config
```
2. Add a new host and set the user and identity file
```shell
Host *github.com
	User Barracoda130
	IdentityFile ~/.ssh/github
```
This is an example. The `*` character means anything under that domain.
3. The token should now be linked. More help can be found by typing `man ssh_config`
