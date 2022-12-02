---
description: Generate a local SSH private / public key pair
---

# SSH access to Siteground space

This step will give you command line access to your new hosting account over the very secure SSH protocol.  This will be essential for the deployment method we are going to use.

If you already have personal SSH key, you can import this into your Siteground account.

### Mac OS / Windows

Follow Siteground SSH instructions [https://www.siteground.co.uk/tutorials/ssh/](https://www.siteground.co.uk/tutorials/ssh/)

### Create a shortcut / alias

You cannot just SSH into your server name, you need to check the credentials within the Siteground control panel

<figure><img src="../.gitbook/assets/Screenshot 2022-12-02 at 21.30.58.png" alt=""><figcaption></figcaption></figure>

Establishing an SSH tunnel takes the form;

`ssh username@hostname -p18765`

Probably best to create an alias or shortcut for this!



