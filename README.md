# Mirrors / Repositories in China 🇨🇳

In Mainland China, using local mirrors is essential due to the Great Firewall (GF), which can significantly slow down or even block access to servers outside of China. By connecting to mirrors within Mainland China, you can get faster update speeds and a more reliable connection when downloading or updating software packages. Additionally, local mirrors are often synchronized with the main repositories, ensuring that you have access to the latest updates and security patches.

## Table of Contents
- [Mirrors / Repositories in China 🇨🇳](#mirrors--repositories-in-china-)
  - [Table of Contents](#table-of-contents)
  - [All in One Script](#all-in-one-script)
  - [Python](#python)
    - [pip](#pip)
    - [conda](#conda)
  - [Docker](#docker)
  - [Helm](#helm)
  - [Terraform](#terraform)
  - [Jenkins](#jenkins)
  - [Homebrew (https://brew.sh )](#homebrew-httpsbrewsh-)
  - [Maven (Java, Scala)](#maven-java-scala)
  - [SBT](#sbt)
  - [NPM (Node.js / JavaScript)](#npm-nodejs--javascript)
  - [Yarn](#yarn)
  - [Gradle (Java)](#gradle-java)
  - [Containerd](#containerd)
  - [Ruby/RubyGems](#rubyrubygems)
  - [Rust/Cargo](#rustcargo)
  - [Go/GoProxy](#gogoproxy)
  - [Flutter/Dart](#flutterdart)
  - [APT/Ubuntu](#aptubuntu)
  - [YUM/CentOS](#yumcentos)
  - [Git](#git)
  - [More mirrors](#more-mirrors)
  - [Additional Resources](#additional-resources)
    - [Mirror Testing Tools](#mirror-testing-tools)
    - [Official Mirror Lists](#official-mirror-lists)
    - [Development Environment Setup](#development-environment-setup)
  - [Contributing](#contributing)
  - [License](#license)

## All in One Script
- [Oh My Tuna](https://tuna.moe/oh-my-tuna/) from [TUNA](https://github.com/tuna)

## Python

### pip
``` pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package ```

### conda
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes


conda update conda 
```

## Docker 

Quay.io: https://quay.azk8s.cn

GCR: https://gcr.azk8s.cn

K8S GCR images: https://registry.aliyuncs.com/google_containers

Docker Hub official: https://registry.docker-cn.com

Docker Hub Azure: https://dockerhub.azk8s.cn

## Helm 

Azure Helm/Kubernetes:  http://mirror.azure.cn/kubernetes/

Alibaba Cloud: https://mirrors.aliyun.com/kubernetes-new/


## Terraform 

Alibaba Cloud Terraform: http://mirrors.aliyun.com/terraform/


## Jenkins 

Azure Jenkins: http://mirror.azure.cn/jenkins/


## Homebrew (https://brew.sh )

Add brew mirror 

```
git -C "$(brew --repo)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

git -C "$(brew --repo homebrew/cask)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git

brew update
```

## Maven (Java, Scala)

Alibaba repo 
```http://maven.aliyun.com/nexus/content/groups/public/```


```
<repositories>
        <repository>
            <id>aliyun</id>
            <url>http://maven.aliyun.com/nexus/content/groups/public</url>
        </repository>
</repositories>
```

## SBT 

~/.sbt/repositories

```
[repositories]
local
aliyun: http://maven.aliyun.com/nexus/content/groups/public/
typesafe: http://repo.typesafe.com/typesafe/ivy-releases/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext], bootOnly
sonatype-oss-releases
maven-central
sonatype-oss-snapshots
```

## NPM (Node.js / JavaScript)
To configure npm to use a mirror:
```
npm config set registry https://registry.npmmirror.com/
npm config get registry
```

## Yarn
To configure Yarn to use a mirror:
```
yarn config set registry https://registry.npmmirror.com/
yarn config get registry
```

## Gradle (Java)
Add in your project's root Gradle settings:
```
repositories {
    maven {
        url "https://maven.aliyun.com/nexus/content/groups/public/"
    }
    // ...existing Gradle repositories...
}
```

## Containerd
You can configure a registry mirror in the containerd config file:
```
[plugins."io.containerd.grpc.v1.cri".registry.mirrors."docker.io"]
  endpoint = ["https://mirror.ccs.tencentyun.com"]
```

## Ruby/RubyGems
To configure RubyGems to use a Chinese mirror:
```bash
# Remove default source
gem sources --remove https://rubygems.org/

# Add Chinese mirror
gem sources -a https://mirrors.tuna.tsinghua.edu.cn/rubygems/

# Verify sources
gem sources -l

# For Bundler
bundle config mirror.https://rubygems.org https://mirrors.tuna.tsinghua.edu.cn/rubygems
```

## Rust/Cargo
Configure Cargo to use Chinese mirrors by editing `~/.cargo/config`:
```toml
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
replace-with = 'tuna'

[source.tuna]
registry = "https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git"

[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"

[source.sjtu]
registry = "https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index"

[source.rustcc]
registry = "https://code.aliyun.com/rustcc/crates.io-index.git"
```

## Go/GoProxy
Configure Go modules proxy for faster downloads:
```bash
# Set GOPROXY
export GOPROXY=https://goproxy.cn,direct

# Or use Alibaba mirror
export GOPROXY=https://mirrors.aliyun.com/goproxy/,direct

# Set GOSUMDB
export GOSUMDB=sum.golang.google.cn

# For permanent configuration, add to ~/.bashrc or ~/.zshrc
echo "export GOPROXY=https://goproxy.cn,direct" >> ~/.bashrc
echo "export GOSUMDB=sum.golang.google.cn" >> ~/.bashrc
```

## Flutter/Dart
Configure Flutter to use Chinese mirrors:
```bash
# Set Flutter mirrors
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn

# For permanent configuration
echo "export PUB_HOSTED_URL=https://pub.flutter-io.cn" >> ~/.bashrc
echo "export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn" >> ~/.bashrc

# Alternative Tsinghua mirrors
export PUB_HOSTED_URL=https://mirrors.tuna.tsinghua.edu.cn/dart-pub/
export FLUTTER_STORAGE_BASE_URL=https://mirrors.tuna.tsinghua.edu.cn/flutter
```

## APT/Ubuntu
Configure APT to use Chinese mirrors for Ubuntu:
```bash
# Backup original sources.list
sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup

# Replace with Tsinghua mirror (Ubuntu 20.04 example)
sudo tee /etc/apt/sources.list <<EOF
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse
EOF

# Update package list
sudo apt update
```

## YUM/CentOS
Configure YUM to use Chinese mirrors for CentOS:
```bash
# Backup original repo files
sudo cp /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

# Download Alibaba mirror configuration
sudo wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo

# Or manually configure with Tsinghua mirror
sudo sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Base.repo
sudo sed -i 's|#baseurl=http://mirror.centos.org|baseurl=https://mirrors.tuna.tsinghua.edu.cn|g' /etc/yum.repos.d/CentOS-Base.repo

# Clean and update cache
sudo yum clean all
sudo yum makecache
```

## Git
Configure Git to use Chinese mirrors for faster clone speeds:
```bash
# GitHub mirror
git config --global url."https://hub.fastgit.xyz/".insteadOf "https://github.com/"

# Or use gitclone.com
git config --global url."https://gitclone.com/github.com/".insteadOf "https://github.com/"

# Reset to original (if needed)
git config --global --unset url."https://hub.fastgit.xyz/".insteadOf
```


## More mirrors 

* Alibaba：http://mirrors.aliyun.com/
* NetEase：http://mirrors.163.com/
* Sohu：http://mirrors.sohu.com/
* Xiamen University: http://mirrors.xmu.edu.cn/
* Shanghai Jiaotong University: http://ftp.sjtu.edu.cn/
* University of Science and Technology of China: http://mirrors.ustc.edu.cn/
* Northeastern University: http://mirror.neu.edu.cn/
* Zhejiang University: http://mirrors.zju.edu.cn/
* Neusoft Institute of Information: http://mirrors.neusoft.edu.cn/
* Tencent: https://mirrors.tencent.com
* Tsinghua University: https://mirrors.tuna.tsinghua.edu.cn/
* Beijing Foreign Studies University: http://mirrors.bfsu.edu.cn/
* Lanzhou University: http://mirror.lzu.edu.cn/
* Harbin Institute of Technology: http://mirrors.hit.edu.cn/
* Nanjing University: http://mirrors.nju.edu.cn/
* China University of Geosciences: http://mirrors.cug.edu.cn/
* Huazhong University of Science and Technology: http://mirrors.hust.edu.cn/
* Dalian University of Technology: http://mirror.dlut.edu.cn/
* Beijing University of Posts and Telecommunications: http://mirrors.bupt.edu.cn/
* Chongqing University: http://mirrors.cqu.edu.cn/
* South China University of Technology: http://mirrors.scut.edu.cn/
* Tianjin University: http://mirror.tju.edu.cn/
* Xidian University: http://linux.xidian.edu.cn/mirrors/

## Additional Resources

### Mirror Testing Tools
- [Mirror Speed Test](https://ping.chinaz.com/) - Test speed to different mirrors
- [Best Mirror](https://www.speedtest.cn/) - Network speed testing

### Official Mirror Lists
- [TUNA Mirror Help](https://mirrors.tuna.tsinghua.edu.cn/help/) - Comprehensive setup guides
- [USTC Mirror Help](https://mirrors.ustc.edu.cn/help/) - University of Science and Technology of China mirrors
- [Alibaba Mirror Help](https://mirrors.aliyun.com/) - Alibaba Cloud mirrors documentation

## Contributing

Feel free to contribute by:
1. Adding new mirrors or repositories
2. Updating existing mirror URLs
3. Adding setup instructions for new tools
4. Reporting broken mirrors

## License

This project is open source and available under the [MIT License](LICENSE).
