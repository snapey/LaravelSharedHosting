# Setting up a CRON job

You will most likely need the scheduler running in order to perform your regular tasks.

Setting up CRON with Siteground is quite easy

From the Site Tools / Devs section, add a new cronjob as below

`cd ~/www/example.org/Live && php81 artisan schedule:run >> /dev/null 2>&1`

Set this with a custom pattern of five start separated by spaces.  This equates to every minute.

<figure><img src="../.gitbook/assets/Screenshot 2022-11-27 at 20.20.32.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
substitute example.org with your domain name
{% endhint %}

