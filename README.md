## Symfony4 starter kit with Docker compose

A docker compose to start a symfony 4 project with php7.2 , mysql and maildev to send emails in dev environment

## Get started

##### Clone the project

    $ git clone https://github.com/dhvarela/symfony4-docker-kit-starter.git
    $ cd symfony4-docker-kit-starter/

##### Run docker-compose to execute all the configurations

    $ docker-compose build

##### Up docker-compose to launch all the containers

    $ docker-compose up -d

Now we could check our containers and we can explore inside of them. For example, let's go inside mysql container:

    $ docker-compose exec mysql sh

#### To create our symfony project, let's go inside the sf4_php container

    $ docker exec -it -u dev sf4_php bash
    $ cd sf4/
    $ composer create-project symfony/website-skeleton my_project

### Copy the project folder to root folder:
     $ cp -Rf /home/wwwroot/sf4/my_project/. .

### Add into gitignore file the old gitignore data:

     ## phpStorm
     .idea

     ## data
     .docker/data/*

#### Remove temporal folder
    $ rm -Rf /home/wwwroot/sf4/my_project/

#### Check permissions to /var folder in symfony project:
    $ chmod -R 777 var/

#### Launch the Symfony application!

http://localhost/