### Installation

Upload the excutable file to a remote CentOS server

```console
$ scp Pool root@yourserverip:/root/pool
```

```console
$ scp HOP root@yourserverip:/root/hop
```


```console
$ chmod +x Pool
$ chmod +x HOP
```

### Add into Bash Profile


```console
$ vi ~/.bash_profile
```

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

>Type ":x" to Save bash_profile and quit.

+ Update Bash Profile

```console
$ source ~/.bash_profile
```



### Prerequisite

!> **Linux Server with fixed IP address**