# SSL Certificate

SiteGround make it absolutely trivial to add a LetsEncrypt free SSL certificate to your server.

Firstly making sure that your domain points to your new site, simply go to **Security** > **SSL Manager** then choose LetsEncrypt from the dropdown and press **GET**

If your server sends out emails with links back to your site (such as password reset) don't forget to change APP\_URL in your master/.env file so that it includes https and then redeploy your site so that the new .env is in place.



