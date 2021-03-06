Multiple SSH Keys settings for different github account
=================================================================


create different public key
---------------------------------

create different ssh key according the article [Mac Set-Up Git](http://help.github.com/mac-set-up-git/)

	$ ssh-keygen -t rsa -C "your_email@youremail.com"

Please refer to [github ssh issues](http://help.github.com/ssh-issues/) for common problems.

for example, 2 keys created at:

	~/.ssh/id_rsa_activehacker
	~/.ssh/id_rsa_jexchan

then, add these two keys as following

	$ ssh-add ~/.ssh/id_rsa_activehacker
	$ ssh-add ~/.ssh/id_rsa_jexchan

you can delete all cached keys before

	$ ssh-add -D

finally, you can check your saved keys

	$ ssh-add -l


Modify the ssh config
---------------------------------

	$ cd ~/.ssh/
	$ touch config
	$ subl -a config

Then added

	#activehacker account
	Host github.com-activehacker
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_activehacker

	#jexchan account
	Host github.com-jexchan
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_jexchan


Clone you repo and modify your Git config
---------------------------------------------

clone your repo
	git clone git@github.com:activehacker/gfs.git gfs_jexchan

cd gfs_jexchan and modify git config

	$ git config user.name "jexchan"
	$ git config user.email "jexchan@gmail.com" 
 
	$ git config user.name "activehacker"
	$ git config user.email "jexlab@gmail.com" 

or you can have global git config
	$ git config --global user.name "jexchan"
	$ git config --global user.email "jexchan@gmail.com"


then use normal flow to push your code

	$ git add .
	$ git commit -m "your comments"
	$ git push



Show git branches ordered by latest commit. Also by name and date.
By commit hash
``` bash
	git for-each-ref --sort=-committerdate refs/heads/
```

By name, date.
``` bash
	git for-each-ref --sort=-committerdate refs/heads/ --format='%(committerdate:short) %(authorname) %(refname:short)'
```
Get a list of existing remote branches
``` bash
git fetch origin
```

Checkout the branch from that branch
``` bash
git checkout -b branch_name origin/branch_name

git pull origin branch_name
git push origin branch_name  # yields 'Everything up-to-date'
```

ssh private key permission check
``` bash
.ssh	drwxr-xr-x	chmod go-w ~/.ssh
	.ssh/id_rsa	-rw-------	chmod go= ~/.ssh/id_rsa
	.ssh/id_rsa.pub	-rw-r--r--	chmod go=r ~/.ssh/id_rsa.pub
	.ssh/config	-rw-r--r--	chmod go=r ~/.ssh/config
```


windows git could use 'pageant' from putty
Add system variable
- GIT_SSH C:\ProgramData\chocolatey\lib\putty.portable\tools\PLINK.EXE
- 
```
To make Pageant automatically run and load keys at startup:

- Find the location of pageant.exe

- Windows key + R to open the 'run' dialog box

- Type: 'shell:startup' in the dialog box

- Create a shortcut to the pageant.exe and put into this startup folder.

- Right click on the shortcut and open 'Properties'

- In 'Target' add: "<route to>/pageant.exe" myprivatekeyname.ppk

- In 'Start in' add: "<route to myprivatekeyname.ppk>" - "<route to>/pageant.exe" myprivatekeyname.ppk myprivatekeyname_2.ppk myprivatekeyname_3.ppk

- Click on the shortcut link and check that Pageant has started and has loaded your keys
```

# submodule/subtree
- https://confluence.atlassian.com/sourcetreekb/adding-a-submodule-subtree-with-sourcetree-785332086.html


Another related article in Chinese

1. http://4simple.github.com/docs/multipleSSHkeys/
2. http://alblue.bandlem.com/2005/08/howto-ssh-logins-using-keys.html
