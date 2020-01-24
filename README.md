# ansible-sbt-deploy

ansibleでdeployする際のテンプレート

## 書き換え場所

#!/bin/bash

app=$1

sed -i "" "s/role-name/$app/" ansible/site.yml
sed -i "" "s/app-bot/$app/" ansible/roles/role-name/vars/main.yml
mv ansible/roles/role-name ansible/roles/$app
mkdir ansible/roles/$app/files
cd ansible/roles/$app/files
ln -fs ../../../../target/universal/$app-0.1.0-SNAPSHOT.zip $app-0.1.0-SNAPSHOT.zip
