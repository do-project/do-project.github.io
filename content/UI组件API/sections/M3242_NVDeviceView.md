---
title: M3242_NVDeviceView 组件
---

### M3242_NVDeviceView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/M3242_NVDeviceView)
 广州宏视流媒体(一个可以远程访问摄像头进行实时监控的组件)

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[loginDevice](#loginDevice)| 登陆当前设备(要登录的设备为属性设置的当前设备),其余方法必须在登录成功之后方可执行
<font color ='#0092db'>异步方法</font>  |[reset](#reset)| 重置搜索参数，也可以用来中断搜索
<font color ='#0092db'>异步方法</font>  |[stopSmartConnection](#stopSmartConnection)| 终止快速配置
<font color ='#0092db'>异步方法</font>  |[startSmartConnection](#startSmartConnection)| 设备的快速网络配置
<font color ='#0092db'>异步方法</font>  |[getLocalDeviceFromLan](#getLocalDeviceFromLan)| 搜索局域网内设备
<font color ='#0092db'>异步方法</font>  |[getInfo](#getInfo)| 根据传入的类型获取当前设备相关信息
<font color ='#0092db'>异步方法</font>  |[setAccountInfo](#setAccountInfo)| 设置账户信息
<font color ='#0092db'>异步方法</font>  |[setDateInfo](#setDateInfo)| 设置日期信息
<font color ='#0092db'>异步方法</font>  |[startPlay](#startPlay)| 开始播放实时预览，其他功能需要在登录方法返回true的情况下才能操作
<font color ='#0092db'>异步方法</font>  |[stop](#stop)| 停止播放实时预览
<font color ='#0092db'>异步方法</font>  |[startSpeak](#startSpeak)| 开启对讲
<font color ='#0092db'>异步方法</font>  |[stopSpeak](#stopSpeak)| 停止对讲
<font color ='#0092db'>异步方法</font>  |[setAudioParam](#setAudioParam)| 音频播放开关
<font color ='#0092db'>异步方法</font>  |[setImageOrientation](#setImageOrientation)| 屏幕倒置设置
<font color ='#0092db'>异步方法</font>  |[screenShot](#screenShot)| 截取当前监控区域显示内容
<font color ='#0092db'>异步方法</font>  |[getRecordFiles](#getRecordFiles)| 根据开始和结束的时间区间获取录制视频列表
<font color ='#0092db'>异步方法</font>  |[startPlayBack](#startPlayBack)| 开始播放录像文件
<font color ='#0092db'>异步方法</font>  |[setPTZAction](#setPTZAction)| 云台控制
<font color ='#0092db'>异步方法</font>  |[callPTZXLocationID](#callPTZXLocationID)| 调用预置位定位
<font color ='#0092db'>异步方法</font>  |[setPTZXLocationID](#setPTZXLocationID)| 设定预置位

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=loginDevice><font color ='#0092db'>**loginDevice**</font></span>: 登陆当前设备(要登录的设备为属性设置的当前设备),其余方法必须在登录成功之后方可执行

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **serverIP** |<font color ='#808000'>**string**</font> | 是 | |
  **port** |<font color ='#808000'>**string**</font> | 是 | |
  **userName** |<font color ='#808000'>**string**</font> | 是 | |
  **password** |<font color ='#808000'>**string**</font> | 是 | |
  **deviceID** |<font color ='#808000'>**string**</font> | 是 | |
  **domainName** |<font color ='#808000'>**string**</font> | 是 | |
  **macAddress** |<font color ='#808000'>**string**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=reset><font color ='#0092db'>**reset**</font></span>: 重置搜索参数，也可以用来中断搜索

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopSmartConnection><font color ='#0092db'>**stopSmartConnection**</font></span>: 终止快速配置

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startSmartConnection><font color ='#0092db'>**startSmartConnection**</font></span>: 设备的快速网络配置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ssid** |<font color ='#808000'>**string**</font> | 是 | |wifi显示的名称
  **password** |<font color ='#808000'>**string**</font> | 是 | |wifi连接密码
  **configID** |<font color ='#808000'>**Integer**</font> | 是 | |搜索的时候必须也用相同的值
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getLocalDeviceFromLan><font color ='#0092db'>**getLocalDeviceFromLan**</font></span>: 搜索局域网内设备

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 设备的ID列表['ID1','ID2'...]
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getInfo><font color ='#0092db'>**getInfo**</font></span>: 根据传入的类型获取当前设备相关信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**number**</font> | 是 | |1、设备信息。2、报警信息。3、时间日期。4、网络信息。5、录像配置信息与设置。6、设备版本以及升级信息。
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 1、设备的信息{'userName':'登录用户名','password':'登录密码'}   2、报警信息{'code':'状态码','hasSoundCtrl':'是否有声音控制','bSoundMainSwitch':'声音总开关','bAlarmAudioSwitch':'报警声音开关','nLanguage':'设备语音提示语言类型','hasExternalIOCtrl':'是否有外报警IO控制','nIOMode':'外部报警IO的工作模式','hasAlarmCtrl':'是否有布防控制','bMotionAlarmSwitch':'运动报警开关,'bPRIAlarmSwitch':'PRI报警开关','bSmokeAlarmSwitch':'烟雾报警开关','bMainAlarmSwitch':'报警总开关'}   3、时间日期{'DateTime':'时间戳到毫秒'}  4、网络信息{''} 5、{'code':'状态码','is1080PEnable':'是否支持1080P','is960PEnable':'是否支持960P','is720PEnable':'是否支持720P','isD1Enable':'是否支持D1(704×576)','isVGAEnable':'是否支持VGA','isCIFEnable':'是否支持CIF(352×288)','isQVGAENable':'是否支持QVGA'} 6、{'saveUserName':'已保存用户名','saveUserPassword':'已保存密码','versionID':'设备版本号','hasUpdate':'是否需要升级','newVersionName':'新版本名','refreshTime':'更新时间','result':'状态码','serverID':'服务器ID','appVersionName':'app版本名','appVersionDate':'app版本日期','kernalVersionName':'内核版本名称','kernalVersionDate':'内核版本日期','hardwareVersionName':'硬件版本名称','hardwareVersionDate':'硬件版本日期'}
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setAccountInfo><font color ='#0092db'>**setAccountInfo**</font></span>: 设置账户信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **userName** |<font color ='#808000'>**string**</font> | 是 | |
  **userPassword** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 设置是否成功：true成功，false失败
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setDateInfo><font color ='#0092db'>**setDateInfo**</font></span>: 设置日期信息

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **date** |<font color ='#808000'>**string**</font> | 是 | |
  **dateType** |<font color ='#808000'>**number**</font> | 否 | |
  **isTimeZoneEnable** |<font color ='#808000'>**boolean**</font> | 否 | |
  **timeZoneIndex** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 设置是否成功：true成功，false失败
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startPlay><font color ='#0092db'>**startPlay**</font></span>: 开始播放实时预览，其他功能需要在登录方法返回true的情况下才能操作

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **channel** |<font color ='#808000'>**number**</font> | 是 | 0|播放通道，通常是0
  **streamType** |<font color ='#808000'>**number**</font> | 是 | 0|码流类型(标清0 高清1)
  **isAudio** |<font color ='#808000'>**boolean**</font> | 是 | true|
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 是否成功：true成功，false失败
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止播放实时预览

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startSpeak><font color ='#0092db'>**startSpeak**</font></span>: 开启对讲

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stopSpeak><font color ='#0092db'>**stopSpeak**</font></span>: 停止对讲

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setAudioParam><font color ='#0092db'>**setAudioParam**</font></span>: 音频播放开关

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **isEnabled** |<font color ='#808000'>**boolean**</font> | 是 | true|true为播放，false为不播放
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setImageOrientation><font color ='#0092db'>**setImageOrientation**</font></span>: 屏幕倒置设置

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **orientation** |<font color ='#808000'>**number**</font> | 是 | 1000|固定只能传1000，摄像头自动决定自己当前的方向
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=screenShot><font color ='#0092db'>**screenShot**</font></span>: 截取当前监控区域显示内容

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回截屏图片保存的地址，是一个data://temp/M3242_NVDeviceView目录下一个图片文件，文件名是日期+时间
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getRecordFiles><font color ='#0092db'>**getRecordFiles**</font></span>: 根据开始和结束的时间区间获取录制视频列表

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **channel** |<font color ='#808000'>**number**</font> | 是 | |
  **searchType** |<font color ='#808000'>**number**</font> | 是 | 0|
  **sYear** |<font color ='#808000'>**number**</font> | 否 | |
  **sMonth** |<font color ='#808000'>**number**</font> | 否 | |
  **sDay** |<font color ='#808000'>**number**</font> | 否 | |
  **sHour** |<font color ='#808000'>**number**</font> | 否 | |
  **sMin** |<font color ='#808000'>**number**</font> | 否 | |
  **sSecond** |<font color ='#808000'>**number**</font> | 否 | |
  **eHour** |<font color ='#808000'>**number**</font> | 否 | |
  **eMin** |<font color ='#808000'>**number**</font> | 否 | |
  **eSecond** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: [{'fileID':'01','fileSize':'文件大小，字节','fileName':'文件名','fileTimeLen':'文件时长'}]
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startPlayBack><font color ='#0092db'>**startPlayBack**</font></span>: 开始播放录像文件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **fileID** |<font color ='#808000'>**number**</font> | 否 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setPTZAction><font color ='#0092db'>**setPTZAction**</font></span>: 云台控制

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **left** |<font color ='#808000'>**boolean**</font> | 否 | true|
  **right** |<font color ='#808000'>**boolean**</font> | 否 | false|
  **up** |<font color ='#808000'>**boolean**</font> | 否 | false|
  **down** |<font color ='#808000'>**boolean**</font> | 否 | false|
  **step** |<font color ='#808000'>**number**</font> | 否 | 1|控制摄像头转动的次数
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 控制摄像头的上下左右方向,哪一个方向为true,就朝哪个方向转动step次,默认朝左转动
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=callPTZXLocationID><font color ='#0092db'>**callPTZXLocationID**</font></span>: 调用预置位定位

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ptzxID** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 返回true或者false
- 说明: 使用当前的登录句柄信息来调用设备到预置位，句柄如下{'result':'登录情况','handle':'登录句柄','ptzxCount':'摇头次数','ptzxPRI':'是否是摇头设备Bool类型','addType':'地址类型','isMRMode':'重连模式','mrServer':'重连地址','domian':'域名','mrPort':'重连端口','macChn':'最大通道','isPRI':'是否有权限','server':'服务器地址','port':'端口','userName':'用户名','password':'密码','isSameLan':'isSameLan','strIP':'strIP','strLanIP':'strLanIP'}
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setPTZXLocationID><font color ='#0092db'>**setPTZXLocationID**</font></span>: 设定预置位

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **ptzxID** |<font color ='#808000'>**number**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: 返回结果值
- 说明: 使用当前的登录句柄信息来设置预置位，句柄如下{'result':'登录情况','handle':'登录句柄','ptzxCount':'摇头次数','ptzxPRI':'是否是摇头设备Bool类型','addType':'地址类型','isMRMode':'重连模式','mrServer':'重连地址','domian':'域名','mrPort':'重连端口','macChn':'最大通道','isPRI':'是否有权限','server':'服务器地址','port':'端口','userName':'用户名','password':'密码','isSameLan':'isSameLan','strIP':'strIP','strLanIP':'strLanIP'}
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


