# Docker stack for Nextcloud and Onlyoffice

## NextCloudOnlyofficeSecureProxy

## Usage

To use this docker-compose stack, you will need to edit the files before the first run of the stack. Plus you will need to create the correct folders somwhere to use for the volumes. The project is loosly based on the Nextcloud github project:

https://github.com/nextcloud/docker

The examples, secure, fpm, proxy ones. I have added in redis, and tweaked the builds for the Dockerfiles to add more features.

The docker-compose file will need to be edited to add the domain names, one for the Nextcloud server, and one for the onlyoffice server (i use a subdomain normally). The default database passwords will need to be chosen. The db.conf file and the nginx.conf file will need to be edited for your server and domains too.

You will need to create the folders for the volumes to map too too.

On first run, the letsencrypt helper will generate all the SSL certs, and the DB and sub folders will be created. Head over to yoru domain and you will be prompted to create an admin user. And then the server will boot up.

Next I add the Nexcloud apps for thumbnail generation, and for only office - setting the middlewar connection. I have seen a bug witht he latest onlyoffice middleware - so I manually install the older stable version, and then DON'T update it!
I then bring the stack down and sudo vim the /config/config.php file to include the additional filetypes thumbnails i want to generate for word files and video files, so the UI is a bit nicer.
