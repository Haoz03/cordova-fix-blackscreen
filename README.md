cordova生成的android应用，启动前，会因为默认的黑色或白色背景，出现闪一下的黑白屏，为了解决这个问题，添加一个默认的背景图，同时screen.png作为cordova默认的启动屏图片，于是背景图设为screen.png
### 使用方法
步骤1——安装本插件：
```
cordova plugin add 本插件路径
 ```

步骤2——打开config.xml，添加配置项：

1. 使用默认启动屏图片
 ```
 <platform name="android">
     <edit-config file="AndroidManifest.xml" mode="merge" target="/manifest/application/activity[@android:name='MainActivity']">
            <activity android:theme="@style/WelcomeStyle" />
     </edit-config>
</platform>
 ```
2. 使用透明颜色
 ```
 <platform name="android">
     <edit-config file="AndroidManifest.xml" mode="merge" target="/manifest/application/activity[@android:name='MainActivity']">
            <activity android:theme="@style/Appwelcome" />
     </edit-config>
</platform>
 ```
二者选其一即可

步骤3——打开config.xml，在widget标签中添加命名空间前缀：

```
<widget xmlns:android="http://schemas.android.com/apk/res/android"> 
```
这样就大功告成了！

> 为什么要引入xmlns:android这个命名空间前缀，是因为config.xml里面用到了这句<activity android:theme="@style/WelcomeStyle" />，不加入无法识别。