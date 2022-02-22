<p align="center">
    <img src="https://static.magento.com/sites/all/themes/magento/logo.svg" width="300px" alt="Magento Commerce" />
</p>

#  Magento 2 Docker to Development

### Features

- Magento 2.4
- Apache
- PHP 7.1, PHP 7.2, PHP 7.3, PHP 7.4
- Xdebug 2.9.8
- MariaDB 10.4.13
- Elasticsearch 7.6
- Varnish 6.4
- Redis
- MailHog
- n98-magerun

| PHP Version  | Composer  | [hirak/prestissimo](https://github.com/hirak/prestissimo) |
|---|---|---|
|7.1|1.10.17|Yes|
|7.2|1.10.17|Yes|
|7.3|1.10.17|Yes|
|7.4|2.*|No|

### Requirements

**Windows:**

Install [Docker](https://www.docker.com/products/docker-desktop) and [WSL Windows Ubuntu 20](https://www.microsoft.com/pt-br/p/ubuntu-2004/9n6svws3rx71?rtc=1&activetab=pivot:overviewtab)

### Before start
Note that for Elasticsearch you need at least 262144 memory. 

To access:
```
wsl -d docker-desktop
```

Once in your docker-desktop, do the following:
```
echo "vm.max_map_count = 262144"> /etc/sysctl.d/999-docker-desktop-conf
```
Followed by:
```
sysctl -w vm.max_map_count=262144
```
You can then exit the docker-host by typing
```
exit
```


**Linux:**

Install [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/) and [Docker-compose](https://docs.docker.com/compose/install/#install-compose).


### Before start
Note that for Elasticsearch you need at least 262144 memory. 

To check:
```
more /proc/sys/vm/max_map_count
```

The vm.max_map_count setting should be set permanently in `/etc/sysctl.conf`:
```
vm.max_map_count=262144
```
After set run:
```
sudo sysctl -p
```


### How to use
Run all containers with command

```
bin/start
```

To install the latest version of Magento 2:

```
bin/shell
rm index.php
install-magento2
```

> If you want to use Varnish use `docker-compose.varnish.yml`
>
> If you don't want to use Varnish and Elasticsearch use `docker-compose.light.yml`

### Panels

**Web server:** http://localhost/

**Local emails:** http://localhost:8025

### Features commands

| Commands  | Description  | Options & Examples |
|---|---|---|
| `bin/init`  | If you didn't use the CURL setup command above, please use this command changing the name of the project.  | `./init MYMAGENTO2` |
| `bin/start`  | If you continuing not using the CURL you can start your container manually  | |
| `bin/stop`  | Stop your project containers  | |
| `bin/kill`  | Stops containers and removes containers, networks, volumes, and images created to the specific project  | |
| `bin/shell`  | Access your container  | `./shell root` | |
| `bin/magento`  | Use the power of the Magento CLI  | |
| `bin/magento-basic`  | All basic Magento CLI commands (setup:upgrade, setup:di:compile, setup:static-content:deploy -f, cache:clean, cache:flush)  | |
| `bin/n98`  | Use the Magerun commands as you want | |
| `bin/grunt-init`  | Prepare to use Grunt  | |
| `bin/grunt`  | Use Grunt specifically in your theme or completely, it'll do the deploy and the watcher.  | `./grunt luma` |
| `bin/xdebug`  |  Enable / Disable the XDebug | |
| `bin/composer`  |  Use Composer commands | `./composer update` |
