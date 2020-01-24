# ansible-sbt-deploy

ansibleでdeployする際のテンプレート

## 書き換え場所

#!/bin/bash

app=$1

sed -i "" "s/role-name/$app/" ansible/site.yml
sed -i "" "s/app-bot/$app/" ansible/roles/role-name/vars/main.yml
mv ansible/role/role-name ansible/role/$app
