Deploy
======

Bash script to handle Git deployment
------------------------------------

After downloading move the deploy file to /usr/local/bin for each access via the terminal command:
deploy

##Deploying to a server:

_Examples can be found within deploy.cfg_

Move the deploy.cfg file to your working directory and changes the values to suit your server setup, for example:
```
#Staging
#===============================
staging_username="USERNAME"
staging_host="host.net"
staging_password="password"
staging_path="/var/stage"
staging_branch="master"

#Production
#===============================
production_username="USERNAME"
production_host="host.net"
production_password="password"
production_path="/var/www"
production_branch="master"
```

###Deployment trigger

Open terminal and navigate to your working directory, from there you may run:

deploy server-name

Using an example from the deploy.cfg snippet above:
```
deploy staging
```
This would log in to the staging server and pull any commits from the master branch.

##Extras

To aid with workflow there's a couple of extras:

###Push

deploy server-name push

Using an example from the deploy.cfg snippet above:
```
deploy staging push
```

This would push all the local commits in the branch specified to the remote repo and deploy to the given server.

###Commit & Push

deploy server-name commit-push

Using an example from the deploy.cfg snippet above:
```
deploy staging commit-push
```

This would make a local commit, asking for a commit message and push all the local commits in the branch specified to the remote repo and deploy to the given server.
