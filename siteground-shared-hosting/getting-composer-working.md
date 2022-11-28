---
description: By default, composer will use PHP7.4 at the command line
---

# Getting composer working

At the time of writing (November 2022), Siteground servers use php7.4 at the command line.

Other php versions are available and are all aliased such as php74, php80, php81

If you want to install your vendor folder with composer (and I suggest that you do) then you need to be able to specify that composer uses the correct version for your project.

### Locate Composer.phar

Composer.phar should be found in the `/usr/local/bin` folder

Type `which composer` to confirm

### Create a Bash Alias

edit the file `~/bashrc` and add the line

`alias composer="php81 /usr/local/bin/composer.phar"`

Now, whenever you log in via SSH, typing composer will run php81 and pass it the composer.phar file

