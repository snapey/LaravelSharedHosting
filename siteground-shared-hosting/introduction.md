# Introduction

SiteGround offer a number of hosting plans.  This guide is for their shared hosting, not virtual private servers (VPS).  They are suitable where you only expect a small number of concurrent users, or want to use the hosting as staging or to test out some design ideas with a client.

These instructions have been tested with their 'Go-Geek' plans, allowing multiple websites to be hosted under the same account.

There looks to be a lot of steps but each is very quick, and most will be needed in all hosting arrangements.

1. Setup the server environment
2. Create a database
3. Clone the code to the server
4. Composer Install the vendor folder
5. Swap running site over to the new deployment

Plus optional steps to add an SSL certificate (why not), create a cron job to run the scheduler, or run a queue.

