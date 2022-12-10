---
description: Best practices for shared hosting Laravel
---

# Some hints and best practices for deploying laravel on shared hosts

## Discuss these articles on GitHub

{% embed url="https://github.com/snapey/LaravelSharedHosting/discussions" %}
Discuss these pages on Github
{% endembed %}

The following articles assist with the deployment of a Laravel project on so called shared hosting accounts.  Many of the techniques are actually from VPS deployments so starting with shared hosting can put knowledge in place for when you need to deploy your growing project to servers with dedicated resources.

## Why shared hosting?

As a solo developer or a small team without DevOps resources, shared hosting can play a useful part in your server resource pool.  Often you can deploy many sites under a single monthly fee (rather than per droplet) meaning you can try out ideas without spinning up additional costs.  Use cases include;

* Staging sites
* Proof of Concept (POC) sites
* Portfolio sites with anticipated low traffic
* Learning resources
* Testing public endpoints for webhooks and hosted APIs

In addition, a shared hosting account can come with resources such as **domain name registration**, **DNS management**, and **Email accounts** and forwarders.  You don't get any of these when purchasing a VPS.  You can use an email account provided by the shared host to send email from your Laravel application rather than trying to use a 'personal' account.

## Contents

* [SiteGround Shared Hosting](siteground-shared-hosting/introduction.md)
