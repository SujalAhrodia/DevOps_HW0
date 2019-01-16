# HW0-DevOps
CSC-519 Spring 2019

Name: Sujal\
Unity Id: ssujal

## Completed Tasks:
### 1. Complete moodle, mattermost, stack overflow profiles by deadline (10)
---
### 2. Github repo and collobrator settings (10)
---
* Screenshot
![](../master/Screenshots/Collaborators.png)
### 3. Opunit checks (20)
---
* Screenshot
![](../master/Screenshots/Opunit_check.png)
### 4. Pipeline workshop (40)
---
### Hook scripts:
### * post-commit:
```shell
#!/bin/sh

open https://google.com/
```
### * pre-commit:
```shell
#!/bin/bash

npm install
# Get the exit code of tests.
if npm test; then
  echo "Passed tests! Commit ✅ allowed!"
  exit 0
fi
echo "Failed npm tests. Canceling 🚫 commit!"
exit 1
```
### * post-receive:
```shell
#!/bin/sh
echo "Current location: $GIT_DIR"
GIT_WORK_TREE=../production-www/ git checkout -f
echo "Pushed to production!"
cd ../production-www
npm install --production
npm run stop
npm run start
```
* Screenshot:
```shell
$ opunit verify local
```
![](../master/Screenshots/Pipeline_Opunit_Checks.png)
* Screenshot: 
Note: After making changes to the message
```shell
git push prod master
```
![](../master/Screenshots/Pipeline_workshop.png)
![](../master/Screenshots/Message_Change.png)
### 5. Screencast (20)
---
![This is a link to my screencast](https://drive.google.com/open?id=1c6PBzQ9BCkprrB0fki-S4O4CqNLf8mp_)
