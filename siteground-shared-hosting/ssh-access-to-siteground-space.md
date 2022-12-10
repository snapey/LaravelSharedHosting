---
description: Generate a local SSH private / public key pair
---

# SSH access to SiteGround space

This step will give you command line access to your new hosting account over the very secure SSH protocol.  This will be essential for the deployment method we are going to use.

If you already have personal SSH key, you can import this into your Siteground account.

### Importing personal key

Under the **Devs** section of Site Tools, Choose SSH Keys Manager and then click the greyed **Import** tab.

Give your imported key a name (for your info only).

Navigate to the folder containing your **public** key and import it.&#x20;

Optionally, you can restrict access to your server via SSH using specific IPs.

### Mac OS / Windows

Follow Siteground SSH instructions [https://www.siteground.co.uk/tutorials/ssh/](https://www.siteground.co.uk/tutorials/ssh/)

### Create a shortcut / alias

You cannot just SSH into your server name, you need to check the credentials within the Siteground control panel

<figure><img src="../.gitbook/assets/Screenshot 2022-12-02 at 21.30.58.png" alt=""><figcaption></figcaption></figure>

Establishing an SSH tunnel takes the form;

`ssh username@hostname -p18765`

Probably best to create an alias or shortcut for this!

After SSH into the server from your terminal, type `ll` to review the directory structure

<figure><img src="../.gitbook/assets/Screenshot 2022-12-10 at 11.39.51.png" alt=""><figcaption></figcaption></figure>

Our Laravel website will be deployed to the www/ folder. `CD` to that folder and `ll`

<figure><img src="../.gitbook/assets/Screenshot 2022-12-10 at 11.42.00.png" alt=""><figcaption></figcaption></figure>

Our website will be deployed to the folder named after your host, in this example `marks364.sg-host.com/`



