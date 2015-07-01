# Gulp training

1. Installing node and npm
2. Installing gulp globally
3. Initialising gulp project
4. Installing gulp locally as a project dependency
5. Installing plugins as a project dependency
6. Creating a basic gulp task
7. Installing missing dependencies
8. Where to look for plugins?
9. Helpful resources

## 1. Installing node and npm

Node.js is a platform built on top of javaScript for easily building fast, scalable network applications. Npm (node package manager) is a handy tool that comes with node to easily manage all add ons via command line. To install, go to node.js package installation file and go through  instructions.

[https://nodejs.org/](https://nodejs.org/)

## 2. Installing gulp globally

You need to do it just onece per machine. Go to terminal and type:

```
sudo npm install gulp -g
```

Password may be required. Type your password, hit enter and wait few seconds. Done!

## 3. Initialising gulp project

This process creates a package.json file in project directory that stores all basic information about node application.

```
npm init
```

## 4. Installing gulp locally as a project dependency

You need to do it just once per project. Go to terminal and type:

```
npm install gulp --save-dev
```

## 5. Installing plugins as a project dependency

You need to do it just once per project. Go to terminal and type:

```
npm install gulp-sass gulp-autoprefixer --save-dev
```

## 6. Creating a basic gulp task

Declaring a new task

```javascript
gulp.task('task_name', function() {
  // instructions
});
```

Adding a source and destination files

```javascript
gulp.task('task_name', function() {
  gulp.src('./sass/style.scss')
    // instructions
    .pipe(gulp.dest('./css'));
});
```

Adding a plugin pipes to task

```javascript
gulp.task('task_name', function() {
  gulp.src('./sass/style.scss')
    .pipe(sass())
    .pipe(autoprefixer())
    .pipe(gulp.dest('./css'));
});
```

## 7. Installing missing dependencies

Just make sure you have your package.json file inside your project directory then go to terminal and type:

```
npm install
```

## 8. Where to look for plugins?

[http://gulpjs.com/plugins/](http://gulpjs.com/plugins/)

## 9. Helpful resources

- [https://github.com/gulpjs/gulp/tree/master/docs](https://github.com/gulpjs/gulp/tree/master/docs)
- [http://leveluptuts.com/tutorials/learning-gulp](http://leveluptuts.com/tutorials/learning-gulp)

If you have any problems to make it work, please ask Pawel for help. He is always more than happy to give you a hand.
