# laravel-ai
使用laravel ai优雅的调用ai客户端

## 安装

~~~
composer require "crisen/laravel-ai":"dev-master"
~~~



### 注册服务提供者

app.php中

~~~

'providers' => [
    
    .....
    
    Crisen\LaravelAi\AiServiceProvider::class,
    
];

'aliases' => [
    
    ....
    'Ai' => Crisen\LaravelAi\Facades\Ai::class,
]
~~~

## 发布资源

~~~
artisan vendor:publish --provider=Crisen\LaravelAi\AiServiceProvider
~~~

### 配置

ai.php

~~~
return [
    
    'default' => 'baidu',


    'drivers' => [
        'baidu' => [
            'app_id' => '15027866', // 百度appid
            'api_key' => 'yGjoCu5KGIssc9l0lbSI25FO', // 百度apikey
            'secret_key' => 'ZPOnxKD9hQ74qPl2rmyp4aBlxEf6lwaB' // 百度secret key
        ],
    ]
];
~~~



### 使用介绍

~~~php+HTML
namespace someNameSpace;

use Crisen\LaravelAi\Facades\Ai;

....

class SomeController{

	public function facesetAdd(){
		//人脸检索
		$res = Ai::face()
		        ->url("jttp://domaon.com/someimgae.jpeg")
		        ->detect();
		 dd($res);
	}
}
~~~



## 更多使用方法

- [详细文档](http://doc.crisen.org/ai)



## 支持的驱动

- 百度AI
- 腾讯优图 (1.0版本给予支持)
- face++ (1.0版本给予支持)



## LICENSE

[MIT](LICENSE)

