# Connect your server to git

Your project will be deployed to the server via `git clone` and for this, your repository needs a deployment key adding into your github account (deployment from Bitbucket or GitLab is very similar, just search for **deploy keys**).

First we need to create a public private key pair on our SiteGround server.

`cd ~/.ssh`

`ssh-keygen -t rsa -P ""` to create an id\_rsa pair with no password. Press enter to use the default filename

You will now have in this folder `id_rsa` and `id_rsa.pub`

You share the contents of `id_rsa.pub` with Github, so `cat` it to the screen and copy the key from the `ssh-rsa` through to the end which finishes with the site name.

Now in github, go to Settings and Deploy Keys

Add a label (eg your domain name) and paste the key you just copied into the key box.

{% hint style="warning" %}
DO NOT check the box for write access.  This server does not need to update your repository.
{% endhint %}

<figure><img src="../.gitbook/assets/Screenshot 2022-11-28 at 18.53.17.png" alt=""><figcaption><p>Key Installed</p></figcaption></figure>

