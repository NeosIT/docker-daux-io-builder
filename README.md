# Builder for daux.io
This Dockerfile is used for the static site documentation generator [daux.io](https://daux.io/) and installs all required dependencies to execute npx, composer and PHP versions.

# Usage
We are using this image for generating and publishing the documentation for our tools. In our *Jenkinsfile* we have something like


	sh "mkdir static"
	sh "chown -R root:root *"
	sh "npm install"
	sh "composer install"
	sh 'npx crafty run --verbose'
	sh "/usr/local/bin/daux generate"

to trigger daux.io