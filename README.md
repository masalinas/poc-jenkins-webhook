## Description
Poc Jenkins WebHook Repo 

## Start ngrok

```shell
ngrok http --host-header=jenkins.dev 8080
```
## Install generic pipeline plugin

![Pipeline plugin](captures/pipeline_plugin.png "Pipeline plugin"

## Configure Github Repository
Configure webhooks

![Webhook configuration](captures/webhook_config.png "Webhook configuration"

## Select pipeline build trigger

Select generic pipeline to trigger the pipeline

- Configure token to select a particular repo in our case: poc-jenkins-webhook

![Pipeline token](captures/pipeline_token.png "Pipeline token"

- Create a variable to control develop pipeline

  -- Set a variable name: develop
  -- Set and expresion based on the POST content sent by github when a push master branch. For github we select the variable called ref

![Post content WebHook](captures/post_github_webhook.png "Post content WebHook"

     The JSONPath expresion will be **$.ref**

  -- Set a filter from using the previous variable

    In our case we must select only the develop branch, will be **refs/heads/develop**

![Develop pipeline config](captures/develop_pipeline_config.png. "Develop pipeline config"

- Create a variable to control new tag in master branch

  -- Set a variable name: tag
  -- Set and expresion based on the POST content sent by github when a push master branch. For github we select the variable called ref
     The JSONPath expresion will be **$.ref**

  -- Set a filter from using the previous variable

    In our case we must select only the tag master branch, will be **^(refs/tags/.+)$**

![Mater Tag pipeline config](captures/tag_master_config.png. "Mater Tag pipeline config"    
