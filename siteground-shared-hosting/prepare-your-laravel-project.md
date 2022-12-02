# Prepare your Laravel project

Nothing special is required to deploy to SiteGround. You should be able to publish your locally developed project directly into SiteGround Shared servers.

{% hint style="info" %}
This process does not include any front-end build process on the server as I prefer to do this within my development environment and the commit built assets.

If you want to do the same with Laravel 9 and Vite, make sure to remove `/public/build` from the .gitignore file in the root of your project.
{% endhint %}
