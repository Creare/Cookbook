# CSS Style Guide

Here at Creare we use [Sass](http://sass-lang.com/) as a preprocessor compiled by Libsass method (C/C++ port of original Ruby Sass). We use [autoprefixer](https://github.com/postcss/autoprefixer) to handle vendor prefixes. Outpus CSS should be compressed.

1. [How to compile Sass via Command Line](#how-to-compile-sass-via-command-line)
2. [Helpful resources](#helpful-resources)

## How to compile Sass via Command Line

### Install Ruby on your computer

First you need to make sure you have a Ruby installed on your computer. If you work on Mac computer, Ruby comes preinstalled. If you are Windows user, download an installer from [that website](http://rubyinstaller.org/). To confirm that Ruby is successfully installed, go to Command Line and type:

```
ruby -v
```

or

```
ruby --version
```
![Install Ruby on your computer](https://raw.githubusercontent.com/Creare/Cookbook/master/CSS/img/1.1.git)

### Install Sass

To install Sass go to Command Line and type:

```
gem install sass
```

On Mac/Linux computer you may be asked about super user permissions. In that case you need to prefix that command with sudo and follow that command by your admin password.

```
sudo gem install sass
```

![Install Sass](https://raw.githubusercontent.com/Creare/Cookbook/master/CSS/img/1.2.git)

To confirm run:

```
sass -v
```

![Install Sass - confirm](https://raw.githubusercontent.com/Creare/Cookbook/master/CSS/img/1.3.git)

### Compile Sass to CSS

In your project directory type:

```
sass --watch input.scss:output.css --style compressed
```

![Compile Sass to CSS](https://raw.githubusercontent.com/Creare/Cookbook/master/CSS/img/1.4.git)

To finish watching process hit Ctrl + C shortcut. Thats it, easy like that.

## Helpful resources

- [CSS Guidelines by Harry Roberts.](http://cssguidelin.es/)
- [Sass Guidelines by Hugo Giraudel](http://sass-guidelin.es/)
- [Sass Tutorials on Level Up Tuts YouTube channel](https://www.youtube.com/playlist?list=PL2CB1F80266E986EA)
