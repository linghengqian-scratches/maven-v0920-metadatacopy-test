# For https://github.com/apache/shardingsphere/issues/21347

- Execute the following commands for comparison in Ubuntu 22.04.
```shell
sudo apt install unzip zip curl sed -y
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk install java 22.3.1.r17-grl
sdk use java 22.3.1.r17-grl
gu install native-image
sudo apt-get install build-essential libz-dev zlib1g-dev -y

git clone git@github.com:linghengqian/maven-v0920-metadatacopy-test.git
cd ./maven-v0920-metadatacopy-test/
./mvnw -Pnative -Dagent=true clean test native:metadata-copy

```