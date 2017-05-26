# Cordova 百度地图定位Android版插件

>本插件是cordova-qdc-baidu-location的升级版,利用百度定位SDK为Web app解决大陆Android定位不准的问题。
>相比原插件，更新百度地图Android版定位SDK（v6.2.3）并提供watchPosition和clearWatch方法。 iOS下并无定位不准问题，可直接使用浏览器定位。
>原插件在此 https://github.com/mrwutong/cordova-qdc-baidu-location ，感谢作者mrwutong

### 一，申请密钥
请参照：[申请密钥Android定位SDK](http://developer.baidu.com/map/index.php?title=android-locsdk/guide/key)

### 二，安装插件

cordova plugin add https://github.com/ChenSunMoon/cordova-sunmoon-location -variable API_KEY="你的ak密钥"

### 三，调用方法
```
// 进行定位
baidu_location.getCurrentPosition(successCallback, failedCallback);
// 连续定位
baidu_location.watchPosition(successCallback, failedCallback, 5); // every 5 seconds
// 停止定位
baidu_location.clearWatch(successCallback, failedCallback);
```
获得定位信息，返回JSON格式数据:
```
{
	"time": "2017-05-26 10:15:29",
	"locType": 161,
	"latitude": 32.141996,
	"longitude": 118.885118,
	"radius": 64.2035140991211,
	"address": {
		"city": "南京市",
		"cityCode": "315",
		"street": "兴智路",
		"streetNumber": "6-2",
		"country": "中国",
		"countryCode": "0",
		"province": "江苏省",
		"district": "栖霞区",
		"describe": "中国江苏省南京市栖霞区兴智路6-2"
	},
	"operators": 0,
	"describe": "网络定位成功"
}
```
具体字段内容请参照：[BDLocation](http://developer.baidu.com/map/loc_refer/index.html)

### 四，查看当前安装了哪些插件
```
cordova plugin ls
```

### 五，删除插件
```
cordova plugin rm cordova.sunmoon.location
```


