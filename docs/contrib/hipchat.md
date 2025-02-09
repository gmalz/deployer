<!-- DO NOT EDIT THIS FILE! -->
<!-- Instead edit contrib/hipchat.php -->
<!-- Then run bin/docgen -->

# Hipchat Recipe

[Source](/contrib/hipchat.php)



## Installing

Add to your _deploy.php_

```php
require 'contrib/hipchat.php';
```

## Configuration

- `hipchat_token` – Hipchat V1 auth token
- `hipchat_room_id` – Room ID or name
- `hipchat_message` –  Deploy message, default is `_{{user}}_ deploying `{{branch}}` to *{{target}}*`
- `hipchat_from` – Default to target
- `hipchat_color` – Message color, default is **green**
- `hipchat_url` –  The URL to the message endpoint, default is https://api.hipchat.com/v1/rooms/message

## Usage

Since you should only notify Hipchat room of a successful deployment, the `hipchat:notify` task should be executed right at the end.

```php
after('deploy', 'hipchat:notify');
```



## Configuration
### hipchat_color
[Source](https://github.com/deployphp/deployer/blob/master/contrib/hipchat.php#L33)



```php title="Default value"
'green'
```


### hipchat_from
[Source](https://github.com/deployphp/deployer/blob/master/contrib/hipchat.php#L34)



```php title="Default value"
'{{target}}'
```


### hipchat_message
[Source](https://github.com/deployphp/deployer/blob/master/contrib/hipchat.php#L35)



```php title="Default value"
'_{{user}}_ deploying `{{branch}}` to *{{target}}*'
```


### hipchat_url
[Source](https://github.com/deployphp/deployer/blob/master/contrib/hipchat.php#L36)



```php title="Default value"
'https://api.hipchat.com/v1/rooms/message'
```



## Tasks

### hipchat:notify
[Source](https://github.com/deployphp/deployer/blob/master/contrib/hipchat.php#L39)

Notifies Hipchat channel of deployment.




