# SSH access to Siteground space

/Generate a local SSH private / public key pair

### Mac OS / Windows

Follow Siteground SSH instructions [https://www.siteground.co.uk/tutorials/ssh/](https://www.siteground.co.uk/tutorials/ssh/)

You cannot just SSH into your server name, you need to check the credentials within the Siteground control panel

<figure><img src="../.gitbook/assets/Screenshot 2022-11-28 at 13.01.20.png" alt=""><figcaption><p>Your details will obviously be different</p></figcaption></figure>

Establishing an SSH tunnel takes the form;

`ssh username@hostname -p18765`



