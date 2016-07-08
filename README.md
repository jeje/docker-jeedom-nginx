# Docker container for Jeedom using Nginx instead of Apache

This is heavily based on the official [Jeedom](http://jeedom.com) installation documentation with Nginx and the official Jeedom container using Apache.

# Starting Jeedom

The easiest way to run Jeedom with this container is to use ``` docker-compose ```.

By default this will start a [MariaDB](https://mariadb.com/) container (for Jeedom data), a [Redis](http://redis.io/) container (for Jeedom Cache) and the web console (this container).

The provided ``` docker-compose ``` file expects two environment variables to be set:
* ``` ROOT_PASSWORD ```: used to define SSH and MariaDB passwords
* ``` MAC_ADDRESS ```: used to define the MAC address of the network device for the web console in order to avoid Jeedom Market activation issues

Here is an example of how to use it:  
``` ROOT_PASSWORD=jeedom MAC_ADDRESS=02:42:ac:11:00:03 docker-compose up -d ```

When done, you'll find Jeedom available on [http://IP_OF_DOCKER:9080].

Then, you'll need to provide the hostname of MariaDB, which will simply be ``` db ```.
You'll need to provide the password you chose before for ``` ROOT_PASSWORD ```.

Jeedom will be up and running after this step.
