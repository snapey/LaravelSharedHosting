---
description: By default, composer will use PHP7.4 at the command line
---

# Getting composer working

At the time of writing (December 2022), Siteground servers use php7.4 at the command line.

{% hint style="info" %}
This might have changed by the time you read this.  Check with `php -v`
{% endhint %}

Other php versions are available and are all aliased such as php74, php80, php81, php82

If you want to install your vendor folder with composer (and I suggest that you do) then you need to be able to specify that composer uses the correct version for your project.

Connect to your server using SSH as per the previous step.

### Locate Composer.phar

Composer.phar should be found in the `/usr/local/bin` folder

Type `which composer` to confirm

### Create a Bash Alias

edit the file `~/.bashrc`&#x20;

You can use the nano editor for this.  Just proceed the file you want to edit with `nano`

```
nano ~/.bashrc
```

and add the line

`alias composer="php81 /usr/local/bin/composer.phar"`

save and exit with `control-o`, `return`, `control-x`

{% hint style="info" %}
You will need to logout and login for the new setting to take effect
{% endhint %}

Now, whenever you log in via SSH, typing composer will run php81 and pass it the composer.phar file

Verify this with `composer diagnose`
