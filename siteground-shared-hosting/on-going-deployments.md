# On-going deployments

The great benefit of this setup is the reliability it brings to the whole deployment process

1. Develop and test locally
2. Commit to your code repository
3. SSH into the server
4. Change to the project folder
5. Run \`./build.sh\`

Your new code will be deployed in under 10 seconds, with no downtime for the users

If you need to run any artisan commands, remember to first switch to the `Live` folder and  run `php81 artisan`(or whatever php value is applicable to your project)
