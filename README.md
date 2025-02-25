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
  - [More mirrors](#more-mirrors)

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
