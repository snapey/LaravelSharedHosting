# Setting up a CRON job

You will most likely need the scheduler running in order to perform your regular tasks.

Setting up CRON with Siteground is quite easy

From the Site Tools / Devs section, add a new cronjob as below

`cd ~/www/smallchart.com/Live && php81 artisan schedule:run >> /dev/null 2>&1`

Set this with a custom pattern of five start separated by spaces.  This equates to every minute.

*

    <figure><img src="https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fnovate%2F1w8QT_w7eE.20.32.png?alt=media&#x26;token=db1302a2-f645-4453-a9dd-6eeee73fec23" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
substitute smallchart.com with your domain name
{% endhint %}

