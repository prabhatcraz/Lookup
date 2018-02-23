# Java
## Taking a heap dump
```jmap -F -dump:format=b,file=/tmp/dump.hprof```

--- 
# Intellij
## Fix case sensitive volume == Edit idea.properties file
Add the following line to idea.properties, on mac it would be like below:
```
vim ~/Library/Preferences/IdeaIC2017.1/idea.properties
idea.case.sensitive.fs=true
```

---
# Operating System
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
# AWS
## Dyanmo
```
for table in $(aws dynamodb list-tables --region eu-west-1 | jq -c -r '.TableNames[]'); do
  aws dynamodb describe-table --region eu-west-1  --table-name ${table}
done
```

---
# Git
##Git lol & lola
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
