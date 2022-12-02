# Running a Queue Worker

Its common that with shared hosting, it is not possible to run supervisor to manage queue workers

One approach for non-time sensitive queue work (such as sending emails) is to add a task to the scheduler that starts the queue worker every minute;

{% code title="Console/Kernel.php" %}
```php
$schedule->command('queue:work --stop-when-empty')
             ->everyMinute()
             ->withoutOverlapping();
```
{% endcode %}

Adding this line to the scheduler in app\Console\Kernel.php and then setting up a cron job to run the scheduler, ensures that the queue gets serviced every minute.

The queue worker will run until there are no more jobs to process and then terminate.  If there is more than one minutes worth of work, then the worker will keep running and the `withoutOverlapping()` function ensures that a second worker is not started if one is already running.
