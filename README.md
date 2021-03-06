# Wechat

可能是目前最优雅的微信公众平台 SDK 了。[Laravel 5 拓展包: overtrue/laravel-wechat](https://github.com/overtrue/laravel-wechat)

[![Build Status](https://travis-ci.org/overtrue/wechat.svg?branch=master)](https://travis-ci.org/overtrue/wechat)
[![Latest Stable Version](https://poser.pugx.org/overtrue/wechat/v/stable.svg)](https://packagist.org/packages/overtrue/wechat)
[![Latest Unstable Version](https://poser.pugx.org/overtrue/wechat/v/unstable.svg)](https://packagist.org/packages/overtrue/wechat)
[![Build Status](https://scrutinizer-ci.com/g/overtrue/wechat/badges/build.png?b=master)](https://scrutinizer-ci.com/g/overtrue/wechat/build-status/master)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/overtrue/wechat/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/overtrue/wechat/?branch=master)
[![Total Downloads](https://poser.pugx.org/overtrue/wechat/downloads)](https://packagist.org/packages/overtrue/wechat)
[![License](https://poser.pugx.org/overtrue/wechat/license)](https://packagist.org/packages/overtrue/wechat)

网上充斥着各种微信 SDK，但是找了一圈，发现没有一个想用，因为没有满足本项目存在后的各种优点：

 - 命名不那么乱七八糟；
 - 隐藏开发者不需要关注的细节；
 - 方法使用更优雅，不必再去研究那些奇怪的的方法名或者类名是做啥用的；
 - 自定义缓存方式；
 - 符合 [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) 标准，你可以各种方便的与你的框架集成；
 - 高度抽象的消息类，免去各种拼json与xml的痛苦。

## 安装

环境要求：PHP >= 5.3.0

1. 使用 [composer](https://getcomposer.org/)

  ```shell
  composer require "overtrue/wechat:~2.*"
  ```

2. 手动安装

  下载 [最新版zip包](https://github.com/overtrue/wechat/archive/master.zip)  或者下载指定版本：https://github.com/overtrue/wechat/releases 。

  然后引入根目录的autoload.php即可：

  ```php
  <?php

  require "wechat/autoload.php"; // 路径请修改为你具体的实际路径

  ...
  ```

## 使用

基本使用（以服务端为例）:

```php
<?php

use Overtrue\Wechat\Server;

$appId          = 'wx3cf0f39249eb0e60';
$token          = 'hellotest';
$encodingAESKey = 'EJThPazwzO4k1cyXJnwQtL60zBdhWvFaHb4emv0dLVN';

$server = new Server($appId, $token, $encodingAESKey);

$server->on('message', function($message){
    return "您好！欢迎关注 overtrue!";
});

// 您可以直接echo 或者返回给框架
echo $server->serve();
```
更多请参考文档。

## 文档

[Wiki](https://github.com/overtrue/wechat/wiki)

> 强烈建议看懂微信文档后再来使用本 SDK。

## Features

- [x] [监听消息](/overtrue/wechat/wiki/接收消息与回复)
- [x] [监听事件](/overtrue/wechat/wiki/监听微信事件)
- [x] [基本消息类型](/overtrue/wechat/wiki/消息的使用)
- [x] [图文消息](/overtrue/wechat/wiki/消息的使用)
- [x] [模板消息](/overtrue/wechat/wiki/模板消息)  `2.0 added`
- [ ] 群发消息 `WIP`
- [x] [用户与用户组](/overtrue/wechat/wiki/用户与用户组管理)
- [x] [客服与消息发送](/overtrue/wechat/wiki/客服管理与发送消息)
- [x] [多客服与消息转发](/overtrue/wechat/wiki/多客服与消息转发)
- [x] [网页授权](/overtrue/wechat/wiki/网页授权)
- [x] [自定义菜单](/overtrue/wechat/wiki/自定义菜单)
- [x] [素材管理](/overtrue/wechat/wiki/素材管理) `2.0 added`
- [x] [门店管理](/overtrue/wechat/wiki/门店管理) `2.0 added`
- [x] [卡券管理](/overtrue/wechat/wiki/卡券) `2.0 added`
- [x] [JSSDK](/overtrue/wechat/wiki/JSSDK) `2.0 added`
- [x] [语义理解](/overtrue/wechat/wiki/语义理解服务) `2.0 added`
- [x] [数据统计](/overtrue/wechat/wiki/数据统计查询服务) `2.0 added`
- [x] [二维码](/overtrue/wechat/wiki/二维码) `2.0 added`
- [x] [短链接](/overtrue/wechat/wiki/短链接) `2.0 added`

## 贡献代码

非常欢迎大家贡献代码共同完善本项目，烦请遵循 [PSR标准](https://github.com/php-fig/fig-standards/blob/master/accepted/) 谢谢！

## License

MIT
