## Node, Bower & Gulp Dockerfile


This repository contains **Dockerfile** of [Node.js](http://nodejs.org/) [Bower](http://bower.io/) & [Gulp](http://gulpjs.com/) runtime for [Docker](https://www.docker.com/).


### Installation

1. Install [Docker](https://www.docker.com/).

2. Build image.
docker build -t gulp .
```sh
	docker build -t gulp .
```

### Usage

This image assumes that your application:

* has a file named [package.json](https://www.npmjs.org/doc/json.html) listing its dependencies.
* has a file named [bower.json](http://bower.io/docs/creating-packages/) listing its dependencies.
* has a file named [Gulpfile.js](https://github.com/gulpjs/gulp/blob/master/README.md) registering `build` task.

Run:

```sh
	docker run -it --rm --name npm -v "$PWD":/var/www -w /var/www gulp npm install
	docker run -it --rm --name bower -v "$PWD":/var/www -w /var/www gulp bower install --allow-root
	docker run -it --rm --name gulp -v "$PWD":/var/www -w /var/www gulp gulp
```
