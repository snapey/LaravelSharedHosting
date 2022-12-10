# The master folder

Create a master folder which will hold

* the .env file to be copied into each deployment
* the storage folder so that it survives deployments

If your website name is **example.org** then navigate to the \~/www/**example.org** folder. Then execute the following;

```shell
mkdir master && cd master && \
mkdir storage && \
mkdir storage/app && \
mkdir storage/app/public && \
mkdir storage/framework && \
mkdir storage/framework/cache && \
mkdir storage/framework/cache/data && \
mkdir storage/framework/sessions && \
mkdir storage/framework/views && \
mkdir storage/logs && \
cd ..
```

This will create the required empty folder structure for your laravel project's storage&#x20;

Files that are stored in this storage folder will persist between deployments and give zero downtime.

{% hint style="warning" %}
Note that this folder structure is within the folder named after your site.
{% endhint %}

