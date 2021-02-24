### BAS Configuration <!-- {docsify-ignore} -->


+ This step is to connect the Pool with BAS network in order to have HOP protocol regonize your new Pool:

```console
$ yum install net-tools -y
```

+ This step is to connect the Pool with BAS network in order to have HOP protocol regonize your new Pool:

```console
$ cd pool
```

+ Download the BAS tool and install into your server under pool folder

```console
$ wget https://docs.hyperorchid.org/_media/BAS_amd64
```

+ change BAS_amd64 tp BAS and change BAS privilege

```console
$ mv BAS_amd64 BAS
```

```console
$ chmod +x BAS
```

+ Start the BAS

```console
$ nohup ./BAS> bas.log 2>&1 &
```

!> Check whether BAS has started tail -f bas.log correctly. If there is no error, it means it has started correctly.
