# Laravel Development with Docker

The instructions are based on this blog-post on medium: [https://medium.com/@shakyShane/laravel-docker-part-1-setup-for-development-e3daaefaf3c](https://medium.com/@shakyShane/laravel-docker-part-1-setup-for-development-e3daaefaf3c)

## Step 1 — grab the latest Laravel release

We’re not following the official guide for setting up Laravel here as we don’t want the hassle of installing PHP/Composer globally on our dev machine.
We will be using curl to download the latest laravel version. The "-L" flag (short for "--location") tells curl to follow any redirects indicating if the target has moved to a new location. The following command downloads the master.tar.gz and pipes its output to tar which uncompresses its content to a folder which is called "laravel-master". Later on you can change the name by invoking the mv command and cd into it. 

```
curl -L https://github.com/laravel/laravel/archive/master.tar.gz | tar xz
mv laravel-master new-project-name
cd new-project-name
```


## Step 2 — Install dependencies

We need to run composer install to pull in all of the libraries that make up Laravel — we can use the composer/composer image from the docker hub to handle this for us.

We’ll create a throw-away container by executing the following command.

`docker run --rm -v $(pwd):/app composer/composer install`

**Notes:**

* We use the `--rm flag to ensure this container does not linger around following the install.
* `-v $(pwd):/app is used to mount the current directory on the host (your cpu) to `/app in the container — this is where composer running inside the container expects to find a `composer.json
* -v $(pwd):/app will also ensure that the vendor folder created by composer inside the container is also visible on our machine.

## Step 3 — create the development docker-compose.yml file



## PHP-FPM


## NGINX



## MYSQL


## All services together



## Starting the services




## Final steps, prepare the Laravel Application.


### Environment configuration file


### Application key & optimize





