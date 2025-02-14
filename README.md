# 基于crisen/laravel-ai 做的衍生版本，如要使用BAIDU_AI，请使用crisen/laravel-ai的包

基于crisen/laravel-ai 做的衍生版本，如要使用BAIDU_AI，请使用crisen/laravel-ai的包

# laravel-ai
使用laravel ai优雅的调用ai客户端

## 安装

~~~
composer require "waimao/laravel-ai":"^1.0.0"
~~~

非laravel版本,[点击这里](https://github.com/crisenchou/ai)

### 配置

app.php中

~~~

//注册服务提供者
'providers' => [
    
    .....
    
    Waimao\LaravelAi\AiServiceProvider::class,
    
];

// 注册facades
'aliases' => [
    
    ....
    
    'Ai' => Waimao\LaravelAi\Facades\Ai::class,
]
~~~

## 发布资源

~~~
artisan vendor:publish --provider=Waimao\LaravelAi\AiServiceProvider
~~~

### 配置

ai.php

~~~
return [
    
    'default' => 'baidu',

    'drivers' => [
        'baidu' => [
            'app_id' => 'your appid', // 百度appid
            'api_key' => 'your api key', // 百度apikey
            'secret_key' => 'your api secret' // 百度secret key
        ],
        'tencent' => [
       	 	'app_id' => 'your appid', // 腾讯appid
       		 'app_key' => 'your secret id', // 腾讯appid
    	]
    ]
];
~~~



### 使用简介

~~~php+HTML
namespace someNameSpace;

use Waimao\LaravelAi\Facades\Ai;

....

class SomeController{

	public function facesetAdd(){
		//人脸检索
		$res = Ai::face()
		        ->url("http://domaon.com/someimgae.jpeg")
		        ->detect();
		 dd($res);
	}
}
~~~



## 更多使用方法

- [详细文档](http://ai.crisen.org)

## 支持的驱动

- 百度AI
- 腾讯AI

## LICENSE

[MIT](LICENSE)

