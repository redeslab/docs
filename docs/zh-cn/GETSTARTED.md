### 安装矿池和矿机

+ 上传可执行程序到Linux服务器,这里使用CentOS作为例子

!>**强烈建议矿池和矿机的服务器独立并且分开，使用同一台服务器会降低矿池和矿机的响应和稳定**

```console
$ curl -o Pool "https://docs.hyperorchid.org/_media/Pool_amd64"
```

```console
$ curl -o Pool "https://docs.hyperorchid.org/_media/HOP_amd64"
```


```console
$ chmod +x Pool
$ chmod +x HOP
```

### 添加Pool和HOP命令到bash_profile


```console
$ vi ~/.bash_profile
```

#### bash_profile配置例子

```
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi

# User specific environment and startup programs

PATH=$PATH:$HOME/bin:~/hop:~/pool

export PATH
```

>输入":x"保存并且退出.

+ 更新bash_profile

```console
$ source ~/.bash_profile
```



### 配置要求

!> **Linux服务器，固定IP或者可以进行公网映射的IP**