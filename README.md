![Magento 2](https://cdn.rawgit.com/rafaelstz/magento2-snippets-visualstudio/master/images/icon.png)

#  Magento 2 Docker to Development

### Apache 2.4 + PHP 7.3 + OPCache + MariaDB 10.4.13 + N98 Magerun 2 + XDebug + Redis + Elasticsearch 7.6.0

### Requirements

**Linux:**

Install [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/) and [Docker-compose](https://docs.docker.com/compose/install/#install-compose).


### Before start
Note that for Elasticsearch you need at least 262144 memory. 

To check:
```
more /proc/sys/vm/max_map_count
```

To increase:
```
sudo sysctl -w vm.max_map_count=262144
```

### How to use
Execute in your terminal, change the _MYMAGENTO2_ to use the name of your project:
```
curl -s https://raw.githubusercontent.com/echo-magento/docker-m2/master/init | bash -s MYMAGENTO2  clone
```

If you want to install the Magento 2, use like that:

```
cd MYMAGENTO2
./shell
rm index.php
install-magento2
```

### Panels

Enjoy your new panels!

**Web server:** http://localhost/

**PHPMyAdmin:** http://localhost:8080

**Local emails:** http://localhost:8025

### Features commands

| Commands  | Description  | Options & Examples |
|---|---|---|
| `./init`  | If you didn't use the CURL setup command above, please use this command changing the name of the project.  | `./init MYMAGENTO2` |
| `./start`  | If you continuing not using the CURL you can start your container manually  | |
| `./stop`  | Stop your project containers  | |
| `./kill`  | Stops containers and removes containers, networks, volumes, and images created to the specific project  | |
| `./shell`  | Access your container  | `./shell root` | |
| `./magento`  | Use the power of the Magento CLI  | |
| `./n98`  | Use the Magerun commands as you want | |
| `./grunt-init`  | Prepare to use Grunt  | |
| `./grunt`  | Use Grunt specifically in your theme or completely, it'll do the deploy and the watcher.  | `./grunt luma` |
| `./xdebug`  |  Enable / Disable the XDebug | |
| `./composer`  |  Use Composer commands | `./composer update` |
