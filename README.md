# Jenkinsfileのサンプル

## 単体テスト

DINDなので、ディレクトリのマッピングがちょっと複雑

```
docker run -it --rm -v /Users/ksaito/work/jenkinsfile:/root/src maven:3.5.4-jdk-8 bash
```

ベースラインは下記のコマンドで作成

```
root@91d36eef22ed:~/src# mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

