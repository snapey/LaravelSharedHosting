---
description: Run our build script from github action such as code release
---

# Deploy using GitHub Actions

Setup a Github action that runs when we release code and uses the build script we created above to deploy to the shared hosting account

### Create SiteGround SSH Key for GitHub Action



### Create Github Action

The details for a GitHub action are stored in a `.yaml` file and will be stored in your code repository under the `.github/workflows` folder.

{% code title="deploy.yaml" lineNumbers="true" %}
```yaml
name: deploy to SiteGround
on:
  workflow_dispatch:
jobs:

  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
    - name: executing remote ssh commands using password
      uses: appleboy/ssh-action@master
      with:
        host: gukm1051.siteground.biz
        username: u1119-ahcvzbcli3ee
        key: ${{ secrets.DEPLOY_RSA_PUBLIC }}
        passphrase: ${{ secrets.DEPLOY_RSA_PASSWORD}}
        port: 18765
        script: |
          cd ~/www/marks364.sg-host.com
          ./build.sh

```
{% endcode %}
