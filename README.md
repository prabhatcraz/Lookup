# Prabhat Ranjan
## Gitlab Setup
### install latest gitlab-runner on ubuntu 
```
apt-get remove gitlab-runner (optional)
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
apt-get install gitlab-runner
```
source - https://gitlab.com/gitlab-org/gitlab-runner/-/issues/4773

## Java
### Taking a heap dump
```jmap -dump:format=b,file=/tmp/dump.hprof```

Note: You might have to run it as the same user which is running the application. so the command may look like:

```sudo sudo -u <app-user> jmap -dump:format=b,file=/tmp/dump.hprof```

---
## Docker
### Remove all untagged images
```docker rmi $(docker images | grep "^<none>" | awk "{print $3}")```
--- 
## Intellij
### Fix case sensitive volume == Edit idea.properties file
Add the following line to idea.properties, on mac it would be like below:
```
vim ~/Library/Preferences/IdeaIC2017.1/idea.properties
idea.case.sensitive.fs=true
```

---
## Operating System
* Find all files more than 100M:
```
find / -xdev -type f -size +100M
```

* Sort folders by size:
```
sudo du max-depth=1 /home/ | sort -n -r
```

* Sort files by size and print size in human readable format:
```
ls -Slh
```

---
## AWS
### Dyanamo DB perform table operation with jq and aws cli
```
for table in $(aws dynamodb list-tables --region eu-west-1 | jq -c -r '.TableNames[]'); do
  aws dynamodb describe-table --region eu-west-1  --table-name ${table}
done
```

---
## Git
### Git lol & lola
Add the following to ~/.gitconfig
```
[alias]
        lol = log --graph --decorate --pretty=oneline --abbrev-commit
        lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
[color]
        branch = auto
        diff = auto
        interactive = auto
        status = auto
```
### Delete all branches other than master
You must be master branch
```
git branch | cat | xargs git branch -d
```

---
## Mac
### Display hidden files
```
defaults write com.apple.finder AppleShowAllFiles TRUE
killall finder
```

---
## ElasticSearch Cheat-sheet
### Create an index
```
curl -X PUT 'http://localhost:9200/user'
```

### Index a document
```
curl -s -H "Content-type: application/json" -XPOST 'http://localhost:9200/onboarding/type' -d '{ "holderid":"123" }'
```
