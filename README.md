# techvomit
[![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/l50/techvomit/blob/master/LICENSE)


This is meant to be used in conjunction with https://github.com/l50/ansible-techvomit.

When run by itself, this will give you a working **Ghost + Nginx + MariaDB + LetsEncrypt** container setup. 

To create the containers on an Ubuntu system, do the following:
1. Install docker and docker-compose - I've done this using an [ansible role](https://github.com/angstwad/docker.ubuntu). You can also use a bash script like [this one](https://gist.github.com/wdullaer/f1af16bd7e970389bad3), or do whatever best suits your needs.
2. Clone into the repo:
```
git clone https://github.com/l50/techvomit.git techvomit && cd techvomit
```
3. Create a .env file in this directory with the parameters required by your various containers:
```
touch .env
```
The contents of the env file should look something like this:
```
URL=yoursitehere
MARIADB_ROOT_PASSWORD=passwordhere
MARIADB_PASSWORD=passwordhere
GHOST_PASSWORD=passwordhere
GHOST_EMAIL=user@user.com
GHOST_USERNAME=usernamehere
BLOG_TITLE=blogtitlehere
```
By doing this, you won't put static credentials into your compose file and accidentally commit them to your public repo. 

4. Once this is done, simply run ```docker-compose up -d``` and you should have a working ghost blog.

## License
MIT

### Resources
- https://blog.agchapman.com/ghost-blog-with-nginx-and-docker-1/
- https://blog.agchapman.com/ghost-blog-with-nginx-and-docker-2/
- https://blog.agchapman.com/upgrading-a-ghost-blog-with-nginx-and-docker-part-3-of-2/
- https://gist.github.com/agc93/b9984b8a3e552632447d60bae16fb6d7
- https://github.com/gregbkr/ghost-nginx-ssl-docker
