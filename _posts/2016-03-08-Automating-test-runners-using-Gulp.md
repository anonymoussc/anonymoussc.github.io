---
title:  "Automating test runners using Gulp"
date:   2016-03-08 10:48:00
summary: Example how to set up and configure Gulp to run the following tasks - HTTP web server, Karma test runner, WebDriver, Protractor.
cover-image: fondos-para_1024.jpg
---

Example how to set up and configure Gulp to run the following tasks - HTTP web server, Karma test runner, WebDriver, Protractor.

### Install Gulp and Protractor globally

    npm install -g gulp protractor

###  Create a package.json

    npm init

### Install dependencies

    npm install connect gulp-load-plugins gulp-protractor karma karma-chrome-launcher karma-jasmine -—save-dev

###  Create Karma configuration file named karma.conf.js

{% highlight JavaScript %}
module.exports = function () {
    
    return {
        frameworks: ['jasmine'],
        files: [
            'lib/angular/angular.js',
            'lib/angular/angular-mocks.js',
            'src/app.js',
            'test/unit/appSpec.js'
        ],
        autoWatch: true,
        browsers: ['Chrome']
    };

};
{% endhighlight %}

### Create a Protractor configuration file named protractor.conf.js

{% highlight JavaScript %}
exports.config = {
    seleniumServerJar: './node_modules/protractor/selenium/selenium-server-standalone-2.41.0.jar',
    specs            : ['test/e2e/appSpec.js'],
    jasmineNodeOpts  : {
        showColors            : true,
        defaultTimeoutInterval: 30000
    }
};
{% endhighlight %}

### Create a file named gulpfile.js

{% highlight JavaScript %}
var gulp = require('gulp');
var $    = require('gulp-load-plugins')();

gulp.task('webdriver_update', $.protractor.webdriver_update);

gulp.task('connect', function() {

    var connect = require('connect');
    var app     = connect().use(connect.static('src'));

    $.server    = require('http').createServer(app).listen(8000);

});

gulp.task('test', function(done) {

    var karma     = require('karma').server;
    var karmaConf = require('./karma.conf.js')();

    karma.start(karmaConf, done);

});

gulp.task('e2e', ['connect', 'webdriver_update'], function(done) {

    gulp.src(['test/e2e/appSpec.js'])
        .pipe($.protractor.protractor({
            configFile: './protractor.conf.js',
        }))
        .on('end', function() {

            $.server.close();
            done();

        });

});
{% endhighlight %}

### Run unit tests

    gulp test

### Run the end-to-end tests

    gulp e2e


---
> Television is simply automated daydreaming.
> <small>- [Lee Loevinger](https://www.brainyquote.com/quotes/quotes/l/leeloeving162532.html)</small>