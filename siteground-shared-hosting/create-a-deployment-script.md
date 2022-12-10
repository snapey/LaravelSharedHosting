# Create a deployment script

The following deployment script performs the following steps

1. Creates a new deployment folder
2. Clones the repository into this deployment folder
3. Copies the .env file from the master folder
4. Runs Composer Install so that the project has the same dependencies as your committed version
5. Creates links for storage to the master storage folder and from storage/app/public to the public/storage folder
6. Finally creates a symlink from Live to the deployment folder

{% code title="build.sh" lineNumbers="true" %}
```bash
#!/bin/sh

UNIX_TIME=$(date +%s)
DEPLOYMENT_DIRECTORY=$UNIX_TIME

PROJECT=$(pwd)

mkdir -p $DEPLOYMENT_DIRECTORY
git clone --depth 1 -b main git@github.com:novateltd/example.org.git $DEPLOYMENT_DIRECTORY

cd $DEPLOYMENT_DIRECTORY

cp ../master/.env .

php81 /usr/local/bin/composer.phar install  --no-dev

cd ..

#link to the latest deployment from Live
ln -v -s -n -f -T $DEPLOYMENT_DIRECTORY Live

# create a link from deployment storage to master/storage
rm -rf $DEPLOYMENT_DIRECTORY/storage
ln -v -s -n -f -T $PROJECT/master/storage $DEPLOYMENT_DIRECTORY/storage


#echo link public to storage
ln -v -s -n -f -T $PROJECT/master/storage/app/public $DEPLOYMENT_DIRECTORY/public/storage

cd Live

php81 artisan cache:clear
php81 artisan route:cache
php81 artisan config:cache

echo Deployed. Migrations required?
echo 
```
{% endcode %}

Copy the above code and create the file in your websites folder using `nano` or the SiteGround file manager.

### Configuring the script for your repo

On line 9, you will need to replace this with the git clone equivalent for your repository and branch.

The parameter `--depth 1` ensures that we don't waste time cloning git history. We only need the latest version of the code.

The parameter `-b main` is the git branch that you would like to deploy.

The project name is the `SSH` version of the clone command for your specific repo.

### php version for Artisan

You can see that this is a PHP8.1 project and all artisan commands must specify the php version to be used.  You may create a bashrc alias for this to revert it to just `php`&#x20;

### Make your script executable

When you create a file, it will not have the execute flag set. You cannot change this from the Site Tools file manager, you must do it from the command line with;

```
chmod +x build.sh
```

You also, cannot run a bash script with just its name, it must be preceded with `./`

So to run the build script, run `./build.sh`&#x20;

### migrating your database

After running the build script for the first time, you will want to migrate your database so that it is ready for action!

All artisan commands should be run from the `Live` folder

```
cd Live
php81 artisan migrate
```

