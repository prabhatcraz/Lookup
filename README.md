# Java
## Taking a heap dump
```jmap -F -dump:format=b,file=/tmp/dump.hprof```
 
#Intellij
## Fix case sensitive volume == Edit idea.properties file
Add the following line to idea.properties, on mac it would be like below:
```vim ~/Library/Preferences/IdeaIC2017.1/idea.properties
idea.case.sensitive.fs=true```



