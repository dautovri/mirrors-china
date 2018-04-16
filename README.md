# Repositories in China

Tsinghua University mirrors (Ubuntu, Fedora, Arch, Debian)

https://mirrors.tuna.tsinghua.edu.cn/


### Python
#### pip 
``` pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package ```

#### conda
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```


### Maven (Java, Scala)

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
