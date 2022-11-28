# Link this site into your webserver

Your site is still not visible.

This is because the SIteGround webserver has its _**document root**_ looking at the public\_html folder.

At this point, many deployment tutorials go horribly wrong by advising you to change the server.php file or to move the contents of the public folder into public html

NO we are NOT going to do that.

We are going to follow a simple two step process

{% hint style="danger" %}
Don't do this if your public\_html folder contains content you need to keep
{% endhint %}

1. delete the public\_html folder `rm -rf public_html`
2. Recreate it as a symlink pointing to the Live/public folder with the command;\
   `ln -s -n -f ~/www/smallchart.com/Live/public public_html`

Now, the contents of public\_html are the same as laravel's public folder and your new site should be Live.

```
```

