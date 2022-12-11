---
description: Run our build script from github action such as code release
---

# Deploy using GitHub Actions

Setup a Github action that runs when we release code and uses the [build script](create-a-deployment-script.md) we created above to deploy to the shared hosting account

### Create SiteGround SSH Key for GitHub Action

In order to authorise GitHub to access your server we need to create an SSH key at SiteGround and then store this in GitHub.  Secrets like this are stored within the repository settings.

Create a new SSH key in SiteGround and make a note of the password that was generated.

Under GitHub **Settings** > **Secrets** > **Actions** add a new secret with the name of `DEPLOY_RSA_PRIVATE`

Copy the **private** key from the SiteGround key just generated

Under GitHub **Settings** > **Secrets** > **Actions** add a new secret with the name of `` DEPLOY_RSA_PASSWORD` ``

Paste in the password noted earlier.

### Create Github Action

The details for a GitHub action are stored in a `.yaml` file and will be stored in your code repository under the `.github/workflows` folder.

{% code title="deploy.yaml" lineNumbers="true" %}
```yaml
name: deploy to SiteGround
on:
  release:
    types: [published, edited]
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
        key: ${{ secrets.DEPLOY_RSA_PRIVATE }}
        passphrase: ${{ secrets.DEPLOY_RSA_PASSWORD}}
        port: 18765
        script: |
          cd ~/www/marks364.sg-host.com
          ./build.sh
```
{% endcode %}

This action spins up an instance of ubuntu server, then connects to your SiteGround website and runs the same commands as are performed if you were to deploy manually.

On line 22, change this to reflect the path to your website.

The above deploy action will be performed automatically when a new code release is created, or you can instigate it manually using the Run Workflow button from the Actions page in GitHub.

