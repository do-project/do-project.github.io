---
title: do_Global 组件
---

### do_Global 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Global)
 Global组件表示手机上的移动应用App的概念，但是和我们的定义的App组件有差别，一个Global下至少包含一个DeviceOne的App组件，但是有可能有多个App组件。这个组件负责一些应用全局的事件，负责应用全局范围内数据的交互和设置。

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getTime](#getTime)| 获取当前设备时间
<font color ='#0092db'>同步方法</font>  |[getWakeupID](#getWakeupID)| 获取应用唤醒ID
<font color ='#0092db'>同步方法</font>  |[getVersion](#getVersion)| 获取应用安装包的版本号
<font color ='#0092db'>同步方法</font>  |[getMemory](#getMemory)| 获取全局变量值
<font color ='#0092db'>同步方法</font>  |[setMemory](#setMemory)| 设置全局变量值
<font color ='#0092db'>同步方法</font>  |[exit](#exit)| 退出应用
<font color ='#0092db'>同步方法</font>  |[setToPasteboard](#setToPasteboard)| 拷贝到粘贴板
<font color ='#0092db'>同步方法</font>  |[getFromPasteboard](#getFromPasteboard)| 从粘贴板取出内容
<font color ='#0092db'>同步方法</font>  |[getSignatureInfo](#getSignatureInfo)| 获取签名证书信息
<font color ='#0092db'>异步方法</font>  |[install](#install)| 安装升级包
<font color ='#e96900'>事件</font>  |[background](#background)| 通常是按手机的home键应用进到后台会触发这个事件
<font color ='#e96900'>事件</font>  |[foreground](#foreground)| 应用从后台回到前台会触发这个事件
<font color ='#e96900'>事件</font>  |[launch](#launch)| 应用被启动会触发这个事件，三种情况 1. 正常点击应用图标启动 2. 被启动应用通过唤醒ID被其他应用唤醒启动 3. 通过点击推送过来的消息来启动 这个事件只能在程序入口脚本代码中订阅才有意义，比如app.lua ,app.js
<font color ='#e96900'>事件</font>  |[broadcast](#broadcast)| android原生系统广播会触发这个事件，当然只有android系统才支持

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getTime><font color ='#0092db'>**getTime**</font></span>: 获取当前设备时间

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **format** |<font color ='#808000'>**string**</font> | 否 | |需要返回的时间格式，比如yyyy-MM-dd这种通用时间格式，如果format为空，返回一个时间的长整型毫秒数
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 当前设备时间
- 说明: 根据用户传递的时间foramt返回格式化的时间。请使用标准的时间格式标记。
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getWakeupID><font color ='#0092db'>**getWakeupID**</font></span>: 获取应用唤醒ID

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 唤醒ID
- 说明: 应用可以被其它应用启动，这个唤醒ID可以在云打包中配置。这个值需要告诉其它第三方应用，让其它应用通过这个唤醒ID来启动我们自己的的应用。同时我们如果知道其它移动应用的唤醒ID，也可以通过我们的External类来启动其他应用
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getVersion><font color ='#0092db'>**getVersion**</font></span>: 获取应用安装包的版本号

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON格式，包含2个值，基本格式如下
{
   'ver':'版本的显示名称，通常是xxx.yyy.zzz格式',
   'code':'版本的build号，是一个唯一序号，通常是一个数字'
}

- 说明: 原生应用安装包的版本，可以通过云打包的过程中设置。通常要实现安装包升级需要调用这个方法，通过比较当前应用的版本和远程服务上最新应用安装包的版本来确定是否需要提示用户升级安装包
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getMemory><font color ='#0092db'>**getMemory**</font></span>: 获取全局变量值

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |变量键值对的key
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 内存中一个变量的值
- 说明: 获取全局变量值，整个应用程序全局的内存共享，在程序的任何位置都可以通过get Memory方法来获取共享数据
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setMemory><font color ='#0092db'>**setMemory**</font></span>: 设置全局变量值

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |
  **value** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置全局变量值，整个应用程序全局的内存共享，在程序的任何位置都可以通过set Memory方法来设置共享数据。如有已经有这个变量名，会覆盖旧的变量值
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=exit><font color ='#0092db'>**exit**</font></span>: 退出应用

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 直接kill进程，退出程序
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=setToPasteboard><font color ='#0092db'>**setToPasteboard**</font></span>: 拷贝到粘贴板

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **data** |<font color ='#808000'>**string**</font> | 是 | |要拷贝的内容
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 拷贝是否成功
- 说明: 拷贝一个字符串到系统的粘贴板共享给其它程序
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getFromPasteboard><font color ='#0092db'>**getFromPasteboard**</font></span>: 从粘贴板取出内容

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 获取的内容
- 说明: 从系统的粘帖板里获取内容
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=getSignatureInfo><font color ='#0092db'>**getSignatureInfo**</font></span>: 获取签名证书信息

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回是一个JSON格式，包含2个值，基本格式如下
{
   'version':'证书版本',
   'serialNumber':'序列号',
   'sigAlgName':'签名算法名称',
   'notBefore':'有效期开始日期',
   'notAfter':'截止日期',
   'SHA256':'SHA256值',
   'SHA1':'SHA1值',
   'MD5':'MD5值',
   'issuerDN':'证书颁发者',
   'subjectDN':'证书拥有者'}

- 说明: 获取签名证书信息，仅支持Android平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=install><font color ='#0092db'>**install**</font></span>: 安装升级包

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **src** |<font color ='#808000'>**string**</font> | 是 | |只能是data://格式的数据文件，而且只能是zip文件
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 安装是否成功
- 说明: DeviceOne提供了程序内升级的功能，也就是不需要升级安装包就能升级业务代码和数据。通常升级包的目录结构必须和build.do文件解开后的目录结构一致，build.do实际上一个zip文件，是通过设计器的“Build Local Package”功能生成的文件，但是升级包只包含变化的文件，最后把升级包压缩成zip文件，再把升级包部署在网络服务上。通过http获取别的方式把升级包下载到我们的data目录下，然后再调用这个install方法，这个方法会解压升级包zip文件到系统目录的升级目录。重启程序，程序每次启动会检查这个升级目录，发现里面有文件就会自动拷贝内容到对应的目录从而实现程序内升级功能
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=background><font color ='#e96900'>**background**</font></span>: 通常是按手机的home键应用进到后台会触发这个事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 通常是按手机的home键应用进到后台会触发这个事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=foreground><font color ='#e96900'>**foreground**</font></span>: 应用从后台回到前台会触发这个事件

- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 
- 说明: 应用从后台回到前台会触发这个事件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=launch><font color ='#e96900'>**launch**</font></span>: 应用被启动会触发这个事件，三种情况 1. 正常点击应用图标启动 2. 被启动应用通过唤醒ID被其他应用唤醒启动 3. 通过点击推送过来的消息来启动 这个事件只能在程序入口脚本代码中订阅才有意义，比如app.lua ,app.js

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 这是一个JSON格式的数据，包含type和data2个节点，格式如下{ 'type':'启动的类型', 'data':'启动被传递的数据' }其中type有4种情况1. 正常启动，该值为空；2. 被其他应用唤醒，该值为'wakeup' 3. 被推送消息启动，该值为'notification'；4. 被本地通知消息启动，该值为'locaLNotification'；而data有3种情况1. 正常启动：这个值为空 2. 被其他应用唤醒：这个值为第三方传递，可以咨询第三方 ，其中andoid需要和第三方约定，唤醒应用的第三方的原生代码里intent需要putStringExtra('data','必须要有值'); 如果第三方也是do平台的应用，可以通过External的openApp方法，方法里的data参数必须要有值3. 被推送消息启动：这个值的格式可以参考我们的推送类
- 说明: 应用被启动会触发这个事件，三种情况 1. 正常点击应用图标启动 2. 被启动应用通过唤醒ID被其他应用唤醒启动 3. 通过点击推送过来的消息来启动 这个事件只能在程序入口脚本代码中订阅才有意义，比如app.lua ,app.js
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=broadcast><font color ='#e96900'>**broadcast**</font></span>: android原生系统广播会触发这个事件，当然只有android系统才支持

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回广播类型type和应用包名content，{type:'PACKAGE_ADDED',content:''}，其中type为PACKAGE_ADDED（安装应用）、PACKAGE_REMOVED（卸载应用）、0（开屏、点亮屏幕）、1（锁屏）、2（解锁）这几种枚举值之一
- 说明: android原生系统广播会触发这个事件，当然只有android系统才支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


