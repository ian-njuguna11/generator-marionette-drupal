[Yeoman](http://yeoman.io) [MarionetteJS](http://marionettejs.com) + [Drupal](drupical.org) generator


- [Application Structure](#application-structure)
- [Getting Started](#getting-started)
    - [Install Generator](#install-generator)
    - [Create a Marionett + Drupal Project](#create-a-marionette-drupal-project)
    - [Execute Sample Application](#execute-sample-application)
    - [Integration with Grunt](#integration-with-grunt)
- [Scaffolding](#scaffolding)
- [ToDo](#todo)
- [Known Issues](#known-issues)



##Application Structure##

```
├── Gruntfile.js
├── bower.json
├── node_modules
├── package.json
└── web ( Configurable: web is recommended)
    ├── 404.html
    ├── favicon.ico
    ├── images
    ├── index.html
    ├── js
        ├── scripts (application scripts)   
    ├── models
    ├── robots.txt
    ├── scripts
    ├── styles
    ├── templates
    ├── vendor ( Configurable: vendor is recommended)
    └── views
```

##Getting Started##

### Install Generator

First make sure you have Node, Npm, Yeoman, Bower, Mocha, phantomJS and Grunt installed.

Visit nodejs.org to install node and NPM

Install phantomJS with:

```bash
$ brew install phantomjs
```
Or visit http://phantomjs.org/


To install Yeoman, Bower and Grunt run: 
```bash
$ npm install -g yo grunt-cli bower
```

Install mocha-phantomjs:

```bash
$ npm install -g mocha-phantomjs
```

Install mocha generator: 

```bash
$ npm install -g generator-mocha-amd
```

Install Marionette Drupal generator

```bash
$ npm install -g generator-marionette-drupal
```

### Create a Marionette Drupal project

Finally, initiate the generator in a empty folder

```bash
$ yo marionette-drupal
```

![yeoman generator](https://raw.githubusercontent.com/enzolutions/generator-marionette-drupal/master/images/yo_marionette_drupal_generator.png "yeoman generator")

You have to define where do you want the app installed *web* is recommended, also you have to define where do you want the Bower components installed *vendor* is recommended.

### Execute sample application

The generator create a simple sample application using an empty model, simple view and render without region.

To execute the sample application you can use the [PHP Built-in web server](http://php.net/manual/en/features.commandline.webserver.php) executing the following command.

```bash
$ php -S localhost:8080
```

After execute that command, you just need open the URL http://localhost:8080 and you will see a similar result as shown in following image.

![yeoman sample application](https://raw.githubusercontent.com/enzolutions/generator-marionette-drupal/master/images/you_marionette_drupal_sample_app.png "yeoman sample application")


The objetive of this sample application is just demostrate the environment is ready to work and you can use the [Scaffolding](#scaffolding) commands to build your application.



### Integration with Grunt

This generator provide a initial Grunt file to execute minimal tasks, you can run all tasks available with following command.

```bash
$ grunt
```

If you prefer you can execute any specific command among listed below.

#### Concat

```bash
$ grunt contact
```

Enable concat all JS files.

Todo: Configure the proper JS files and enable CSS files

#### Uglify

```bash
$ grunt uglify
```

Minify JS file combined in Contact tasks.

Todo: Configure minify for CSS files.

#### Imagemin

```bash
$ grunt imagemin
```

Optimize images in your project.

#### Compass

```bash
$ grunt compass
```

Enable process SASS files to generate CSS files in your project. This project include [bootstrap-sass](https://github.com/twbs/bootstrap-sass)

#### Watch

```bash
$ grunt watch
```

Monitor when SASS files are modified to generate new CSS files.

##Scaffolding##

### Generate a template

```bash
$ yo marionette-drupal:tmpl name
```

This command will create an empty template inside application folder [app_folder]/*templates*

### Generate a Model
```bash
$ yo marionette-drupal:model name
```

This command will create a simple Backbone module to be used in combination with a View

### Generate a View
```bash
$ yo marionette-drupal:view name [--with-template]
```

This command will create a Marionette ItemView, optionally is possible create a template with the same name of view auto related with this template.

When a template is related with a view, Twig.js is used to render the template.


##ToDO##

- Improve Drupal Model Scaffolding command
- Improve View Scaffolding command
- Create Drupal Collection Scaffolding command
- Create Region Scaffolding command
- Create Layout Scaffolding command

##Known Issues##

When  you are trying to create you application, the combination of dependencies between packages require you define what version os underscore you want to install and you will get a message similar to following image.

![yeoman generator conflicts](https://raw.githubusercontent.com/enzolutions/generator-marionette-drupal/master/images/yo_marionette_drupal_resolving_conflict.png "yeoman generator conflicts")

If you only see the question mark symbol, without any indication, you need to change the log level of npm using the folowing command.

```
$ npm config set loglevel error
```
