---
title: "Webhook"
linkTitle: "Webhook"
weight: 3
bookFlatSection: true
---
# [Webhook](#Webhook)
desc: A Webhook is a plugin instance receiving data from external monitoring systems.


>  **Package : spaceone.api.monitoring.v1**

<br>
<br>

## Webhook





**Webhook Methods:**


| Method | Request | Response |
| :----- | :-------- | :-------- |
| [**create**](./Webhook#create) | [CreateWebhookRequest](Webhook#createwebhookrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**update**](./Webhook#update) | [UpdateWebhookRequest](Webhook#updatewebhookrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**update_plugin**](./Webhook#update_plugin) | [UpdateWebhookPluginRequest](Webhook#updatewebhookpluginrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**verify_plugin**](./Webhook#verify_plugin) | [WebhookRequest](Webhook#webhookrequest) | [Empty](./Webhook#empty) |
| [**enable**](./Webhook#enable) | [WebhookRequest](Webhook#webhookrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**disable**](./Webhook#disable) | [WebhookRequest](Webhook#webhookrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**delete**](./Webhook#delete) | [WebhookRequest](Webhook#webhookrequest) | [Empty](./Webhook#empty) |
| [**get**](./Webhook#get) | [GetWebhookRequest](Webhook#getwebhookrequest) | [WebhookInfo](./Webhook#webhookinfo) |
| [**list**](./Webhook#list) | [WebhookQuery](Webhook#webhookquery) | [WebhooksInfo](./Webhook#webhooksinfo) |
| [**stat**](./Webhook#stat) | [WebhookStatQuery](Webhook#webhookstatquery) | [Struct](./Webhook#struct) |



    
<br>

### create

desc: Creates a new Webhook. A Webhook collects data from an external monitoring system with a webhook URL generated by the resource.
request_example: >-
{
"name": "aws-sns-webhook-for-phd",
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"options": {}
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-phd",
"state": "ENABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
}



> **POST** /monitoring/v1/webhook/create
>






    
<br>

### update

desc: Updates a specific Webhook. You can make changes in Webhook settings, including the name and tags.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"state": "ENABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
}



> **POST** /monitoring/v1/webhook/update
>






    
<br>

### update_plugin

desc: Updates the plugin of a specific DataSource. You can change the `version` of the plugin and select the `upgrade_mode` among `AUTO`, `MANUAL`, and `NONE`.
request_example: >-
{
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "AWS-SNS-Webhook",
"state": "ENABLED",
"access_key": "1234567890121234567890121234",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890121234567890121234/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T09:13:16.723Z"
}



> **POST** /monitoring/v1/webhook/update-plugin
>






    
<br>

### verify_plugin

desc: Verifies a specific plugin for a Webhook.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"domain_id": "domain-123456789012"
}



> **POST** /monitoring/v1/webhook/verify-plugin
>






    
<br>

### enable

desc: Enables a specific Webhook. By enabling a Webhook, you can communicate with an external application.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"state": "ENABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
}



> **POST** /monitoring/v1/webhook/enable
>






    
<br>

### disable

desc: Disables a specific Webhook. By disabling a Webhook, you cannot communicate with an external application, as the webhook URL from the Webhook becomes invalid.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"state": "DISABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
}



> **POST** /monitoring/v1/webhook/disable
>






    
<br>

### delete

desc: Deletes a specific Webhook. By deleting a Webhook, you cannot collect data from an external monitoring system, as the `REST URL` is also deleted.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"domain_id": "domain-123456789012"
}



> **POST** /monitoring/v1/webhook/delete
>






    
<br>

### get

desc: Gets a specific Webhook. Prints detailed information about the Webhook, including the name, the version, and the created datetime.
request_example: >-
{
"webhook_id": "webhook-123456789012",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"state": "ENABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
}



> **POST** /monitoring/v1/webhook/get
>






    
<br>

### list

desc: Gets a list of all Webhooks. You can use a query to get a filtered list of Webhooks.
request_example: >-
{
"query": {},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012"
}
response_example: >-
{
"results": [
{
"webhook_id": "webhook-123456789012",
"name": "aws-sns-webhook-for-cloudwatch",
"state": "ENABLED",
"access_key": "1234567890123456789012345678901",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-123456789012/1234567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-aws-sns-mon-webhook",
"version": "1.2.2",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:23:33.875Z"
},
{
"webhook_id": "webhook-987654321098",
"name": "zabbix-webhook",
"state": "ENABLED",
"access_key": "9876567890123456789012345678901",
"webhook_url": "https://monitoring-webhook.dev.spaceone.dev/monitoring/v1/webhook/webhook-987654321098/9876567890123456789012345678901/events",
"capability": {},
"plugin_info": {
"plugin_id": "plugin-zabbix-mon-webhook",
"version": "1.0",
"options": {},
"metadata": {},
"upgrade_mode": "AUTO"
},
"project_id": "project-123456789012",
"domain_id": "domain-123456789012",
"created_at": "2022-01-01T07:42:31.872Z"
}
],
"total_count": 2
}



> **POST** /monitoring/v1/webhook/list
>






    
<br>

### stat





> **POST** /monitoring/v1/webhook/stat
>






    


<br>
<br>

## Message



### CreateWebhookRequest
* **name** (string)  `Required` 

  *is_required: true*

    
* **plugin_info** (WebhookPluginInfo)  `Required` 

  *is_required: true*

    
* **tags** (Struct)  `Required` 

  *is_required: false*

    
* **project_id** (string)  `Required` 

  *is_required: true*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### GetWebhookRequest
* **webhook_id** (string)  `Required` 

  *is_required: true*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    
* **only** (string)  `Required` 

  *is_required: false*

    <br>

### UpdateWebhookPluginRequest
* **webhook_id** (string)  `Required` 

  *is_required: true*

    
* **version** (string)  `Required` 

  *is_required: false*

    
* **options** (Struct)  `Required` 

  *is_required: false*

    
* **upgrade_mode** (UpgradeMode)  `Required` 

  *is_required: false*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### UpdateWebhookRequest
* **webhook_id** (string)  `Required` 

  *is_required: true*

    
* **name** (string)  `Required` 

  *is_required: false*

    
* **tags** (Struct)  `Required` 

  *is_required: false*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### WebhookInfo
* **webhook_id** (string)  `Required` 

    
* **name** (string)  `Required` 

    
* **state** (WebhookState)  `Required` 

    
* **access_key** (string)  `Required` 

    
* **webhook_url** (string)  `Required` 

    
* **capability** (Struct)  `Required` 

    
* **plugin_info** (WebhookPluginInfo)  `Required` 

    
* **tags** (Struct)  `Required` 

    
* **project_id** (string)  `Required` 

    
* **domain_id** (string)  `Required` 

    
* **created_at** (string)  `Required` 

    <br>

### WebhookPluginInfo
* **plugin_id** (string)  `Required` 

    
* **version** (string)  `Required` 

    
* **options** (Struct)  `Required` 

    
* **metadata** (Struct)  `Required` 

    
* **upgrade_mode** (UpgradeMode)  `Required` 

    <br>

### WebhookQuery
* **query** (Query)  `Required` 

  *is_required: false*

    
* **webhook_id** (string)  `Required` 

  *is_required: false*

    
* **name** (string)  `Required` 

  *is_required: false*

    
* **state** (WebhookState)  `Required` 

  *is_required: false*

    
* **access_key** (string)  `Required` 

  *is_required: false*

    
* **webhook_url** (string)  `Required` 

  *is_required: false*

    
* **project_id** (string)  `Required` 

  *is_required: false*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### WebhookRequest
* **webhook_id** (string)  `Required` 

  *is_required: true*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### WebhookStatQuery
* **query** (StatisticsQuery)  `Required` 

  *is_required: true*

    
* **domain_id** (string)  `Required` 

  *is_required: true*

    <br>

### WebhooksInfo
* **results** (WebhookInfo)  `Required` 

    
* **total_count** (int32)  `Required` 

    <br>