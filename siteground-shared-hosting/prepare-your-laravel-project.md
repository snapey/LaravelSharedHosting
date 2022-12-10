# Prepare your Laravel project

Nothing special is required to deploy to SiteGround. You should be able to publish your locally developed project directly into SiteGround Shared servers.

{% hint style="info" %}
This process does not include any front-end build process on the server as I prefer to do this within my development environment and the commit built assets.

If you want to do the same with Laravel 9 and Vite, make sure to remove `/public/build` from the .gitignore file in the root of your project.
{% endhint %}

### Version Control

This guide relies on deploying from a GIT flavoured repository (Gitlab / Github / BitBucket) so make sure you are committing your source code when it is ready to be deployed.  In the [deployment script](create-a-deployment-script.md) you will specify the name of the branch you wish to deploy from so you could deploy from _main_/_master_ or _deploy_ for instance.

{% hint style="danger" %}
Your **.env** file should **NOT** be part of your committed code.
{% endhint %}

