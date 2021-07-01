# Use Docker to create a local WordPress development environment

These files are used in a tutorial I created on my website, [www.massolit-media.com](https://www.massolit-media.com) that introduces the reader to Docker and demonstrates how you can create your own WordPress environment using Docker, Docker Compose, and Dockerfiles.

An overview of the tutorial: [Use Docker to create a local WordPress development environment](https://www.massolit-media.com/technical-writing/local-wordpress-development-environment-with-docker/)

The five articles that this tutorial consists of are designed to be read and completed in sequence, but they do not have to be:
1. [WordPress and Docker: Introduction to Docker and basic Docker commands](https://www.massolit-media.com/tech-writing/wordpress-and-docker-introduction-to-docker/) – Get started using Docker on the command line.
2. [WordPress and Docker: Using Docker Compose](https://www.massolit-media.com/tech-writing/wordpress-and-docker-using-docker-compose/) – Create your own Docker application that uses three containers to create a WordPress site that you can deploy wherever you can run Docker and Docker Compose.
3. [WordPress and Docker: Customizing a Docker container](https://www.massolit-media.com/tech-writing/wordpress-and-docker-customize-a-container/) – Open up some containers and work on them. Then save your work.
4. [WordPress and Docker: Build custom images with Dockerfiles](https://www.massolit-media.com/tech-writing/wordpress-and-docker-dockerfiles/) – Build containers with an automated workflow defined in a text file so the container has what you want in it without you having to open it.
5. [WordPress and Docker: Putting it all together](https://www.massolit-media.com/tech-writing/wordpress-and-docker-conclusion/) – Making some final changes to a Docker Compose file to deploy the entire application with a single command.

## Prerequisites

This tutorial requires you to have some familiarity with and knowledge of the Linux command line, including text editors like Vi/Vim or Nano. I created this tutorial using:
* A MacBook Pro (macOS 10.14)
* The macOS Terminal with Zsh.
* A text editor. I like Visual Studio Code.
* Docker Desktop for Mac. Docker Community Edition, the free version of Docker, is available for Windows and Linux and can also be run on AWS or Azure. [Find Docker CE for your platform](https://hub.docker.com/search?type=edition&amp;offering=community).
* This GitHub repo.

## Contents of this Repo

### Directory Tree

```bash
.
├── README.md
├── docker
│   ├── dockerfiles
│   │   ├── phpmyadmin
│   │   │   ├── dockerfile
│   │   │   └── php.ini
│   │   └── wordpress
│   │       ├── dockerfile
│   │       └── php.ini
│   ├── wp
│   │   └── docker-compose.yml
│   └── wp_final
│       └── docker-compose.yml
└── docker-compose-commented.yml
```

### Description

* `README.md`: This README file.\
* `docker`: In the tutorial, I suggest the reader create a directory for all Docker projects.\
  * `dockerfiles`: Directories for two Dockerfiles, described in [WordPress and Docker: Build custom images with Dockerfiles](https://www.massolit-media.com/teßch-writing/wordpress-and-docker-dockerfiles/).\
     * `phpmyadmin`: Create a customized phpMyAdmin image.\
        * `dockerfile`: Dockerfile to create a customized phpMyAdmin image.\
        * `php.ini`: A PHP.ini file to include in the new image using the `COPY` instruction.\
     * `wordpress`: Create a customized WordPress image.\
        * `dockerfile`: Dockerfile to create a customized phpMyAdmin image.\
        * `php.ini`: A PHP.ini file to include in the new image using the `COPY` instruction.\
  * `wp`: I suggest the reader create individual directories for each Docker Compose project. `wp` for WordPress.\
     * `docker-compose.yml`: A Docker Compose project discussed in [WordPress and Docker: Using Docker Compose](https://www.massolit-media.com/tech-writing/wordpress-and-docker-using-docker-compose/).\
  * `wp_final`: A final version of a Docker Compose project that creates a local WordPress environment.\
    * `docker-compose.yml`: A Docker Compose project discussed in [WordPress and Docker: Putting it all together](https://www.massolit-media.com/tech-writing/wordpress-and-docker-conclusion/). This version includes a configuration that will build images from Dockerfiles before creating the network and containers.\
* `docker-compose-commented.yml`: A heavily commented version of the Docker Compose file from [WordPress and Docker: Using Docker Compose](https://www.massolit-media.com/tech-writing/wordpress-and-docker-using-docker-compose/).