Setup different github accounts in the same computer
=================================================================


# WAY-1


Create a New SSH Key
---------------------------------

create a ssh key for each account

	$ ssh-keygen -t rsa -C "EMAIL_ID_HERE"


Attach the New Key
---------------------------------


create a ssh key for each account

	$ ssh-keygen -t rsa -C "EMAIL_ID_HERE"


Attach the new key, within the "SSH Public Keys" section in github by doing

    vim ~/.ssh/id_rsa_COMPANY.pub

We saved our new ssh key with different name. Let github know about it.

    ssh-add ~/.ssh/id_rsa_COMPANY




Create a config
---------------------------------

we need a way to specify when we wish to push to our personal account, and when we should instead push to our company account. To do so, let's create a config file.

    touch ~/.ssh/config
    vim config


    #Default GitHub
    Host github.com
      HostName github.com
      User git
      IdentityFile ~/.ssh/id_rsa

This is the default setup for pushing to our personal GitHub account. Notice that we're able to attach an identity file to the host. Let's add another one for the company account

    Host github-COMPANY
      HostName github.com
      User git
      IdentityFile ~/.ssh/id_rsa_COMPANY


Add remote urls
------------------------------------

    git remote add origin git@github.com:vinaybokam/configs-commands-installations.git
    git remote add origin git@github-COMPANY:bokamvinaykumar/configs-commands-installations.git



# WAY-2


we can even setup emailid and user name for that specific repo by the following way


Setting your email address for every repository on your computer
-----------------------------------------------------------------


    $ git config --global user.name "GIT_USER_NAME_HERE"
    $ git config --global user.email "GIT_EMAIL_HERE"


Setting your email address for single repo
-----------------------------------------------------------------


You can change the email address associated with commits you make in a single repository. This will override your global Git config settings in this one repository, but will not affect any other repositories.

    $ git config user.name "GIT_USER_NAME_HERE"
    $ git config user.email "GIT_EMAIL_HERE"


