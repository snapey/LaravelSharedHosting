---
description: We can trigger remote deployment over SSH
---

# Deploy from local development

With the addition of one small package and an additional artisan command we can create a `php artisan build` command which can be run from the local development environment and cause a deployment on the production server over SSH

### Spatie' Remote SSH Runner

Install the package [https://github.com/spatie/ssh](https://github.com/spatie/ssh) as a development dependency (we will never need this in production).

```shell
composer require spatie/ssh --dev
```

### Build Console Command

{% code title="app/Console/Commands/Build.php" lineNumbers="true" %}
```php
<?php

namespace App\Console\Commands;

use Spatie\Ssh\Ssh;
use Illuminate\Console\Command;

class Build extends Command
{
    protected $signature = 'build';

    protected $description = 'Run the build command on the remote server';

    protected $server = 'gukm1051.siteground.biz';
    protected $account = 'u1119-ahcvzbcli3ee';
    protected $port = 18765;
    protected $path = '~/www/marks364.sg-host.com';

    public function handle()
    {
        $this->comment('starting build on remote server');
        $this->warn('---------------------------------------------------');

        $process = Ssh::create($this->account, $this->server, $this->port)
        ->onOutput(function($type, $line){
            $this->line($line);
        })
        ->execute([
            'cd ' . $this->path,
            './build.sh'
        ]);

        $this->warn('---------------------------------------------------');

        if($process->isSuccessful()) {
            $this->comment('Successfully Finished Deployment');
            $this->newline();
            return Command::SUCCESS;
        } else {
            $this->error('Deployment failed');
            $this->newline();
            return Command::FAILURE;
        }
        
    }
}

```
{% endcode %}

Add this file into your project then configure lines 14 to 16 for the hosts SSH connection and then add the folder for your remote website on line 17.

Now, after making changes to your project and pushing to your repository, you can locally run&#x20;

`php artisan build`&#x20;

and your site will be deployed with feedback from the remote server on your console.
