# Slack Notification

Github [composite action](https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/creating-a-composite-run-steps-action) that configures local openssh with provided host and credentials.

### Instructions 

Add the action call to your build script YAML and provide your SSH credentials and private key: 

```yaml
  - name: Set up SSH
    uses: PressCentric/Action-Setup-SSH@master
    with:
      server-name: dev
      host: ${{ secrets.SSH_DEV_HOST }}
      port: ${{ secrets.SSH_DEV_PORT }}
      user: ${{ secrets.SSH_DEV_USER }}
      private-key: ${{ secrets.SSH_DEV_PRIVATE_KEY }}
```

then you can simply run

```shell script
ssh dev 'pwd'
scp text.txt dev:/target-dir/
``` 

