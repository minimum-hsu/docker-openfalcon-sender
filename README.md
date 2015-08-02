# docker-openfalcon-sender

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-sender .
```

## Run

### Basic Run

Use default configuration, and falcon-sender package.

```
$sudo docker run -dti --name sender -p 6066:6066 openfalcon-sender
```

### Advanced Run

+ Self-defined configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Sender](http://book.open-falcon.com/zh/install/sender.html).

+ New falcon-sender package

    Replace file **falcon-sender.tar.gz** in the volume */package*.
    
For example, **cfg.json** in /tmp/config and **falcon-sender.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name sender -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 6066:6066 openfalcon-sender
```
