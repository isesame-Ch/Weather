<h1 align="center"> weather </h1>

<p align="center"> A weather SDK.</p>

[![Build Status](https://travis-ci.com/isesame-Ch/Weather.svg?branch=master)](https://travis-ci.com/isesame-Ch/Weather)
## Installing

```shell
$ composer require isesame/weather -vvv
```

## Usage

1. 在配置本拓展前，请先前往[高德地图开放平台官网](https://lbs.amap.com)注册账号并创建应用，获取到应用的```ak```值
2. 使用方法
      ```php
      $key = 'bb5e3bd493d1f29f52f9d8ee4bf47049';
      $w = new \Isesame\Weather\Weather($key);
   
      $w->getLiveWeather('深圳');
      $w->getForecastsWeather('深圳','xml');
      ```
3. 在laravel中已经注册为服务，需要在config/services.php中配置
   ```
   ...
   
   'weather' => [
       'key' => env('WEATHER_API_KEY'),
   ],
   
   ...
   ```
   并在env中添加对应的高德应用key,即可使用
   ```php
   app('weather')->getLiveWeather('深圳');
    
   或
   
   public function show(Request $request, Weather $weather, $city)
   {
       return $weather->getWeather($city);
   } 
   ```

## Contributing

You can contribute in one of three ways:

1. File bug reports using the [issue tracker](https://github.com/isesame/weather/issues).
2. Answer questions or fix bugs on the [issue tracker](https://github.com/isesame/weather/issues).
3. Contribute new features or update the wiki.

_The code contribution process is not very formal. You just need to make sure that you follow the PSR-0, PSR-1, and PSR-2 coding guidelines. Any new code contributions must be accompanied by unit tests where applicable._

## License

MIT