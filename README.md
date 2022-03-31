# uniapp-build-packges

uniapp本地打包

## 基础环境
1. 依赖: JRE, gradle, uni-app SDK
2. 软件: Android Studio, HBuilderX


## 打包 (uni-app SDK与HBuilderX版本必须保持一致)
**Build** -> **Generate Signed Bundle/APK...**

****

## 文件配置
1. Androidmanifest.xml (/simpleDemo/src/main/AndroidManifest.xml)

**android:value** appKey字符串

```
<meta-data
            android:name="dcloud_appkey"
            android:value="你的appKey" />
```

2. build.gradle (/simpleDemo/build.gradle)

   2.1 包名及版本
   **applicationId** 包名 字符串

   **versionCode** 主版本 字符串

   **versionName** 版本号 字符串

   *以上3个字段要与HBuildX一致*

    ```
    defaultConfig {
            applicationId "com.bzkj.mobile.portal"
            minSdkVersion 21
            targetSdkVersion 28
            versionCode 4
            versionName "1.1.0"
            multiDexEnabled true
            compileOptions {
                sourceCompatibility JavaVersion.VERSION_1_8
                targetCompatibility JavaVersion.VERSION_1_8
            }
        }
    ```

   2.2 证书 SHA1须与dCloud开发者中心一致

   **keyAlias** 别名 字符串

   **keyPassword** 密码 字符串

   **storePassword** 同上 字符串

   **storeFile** 证书路径 字符串

   ```
   signingConfigs {
           config {
               keyAlias 'ybsj.keystore'
               keyPassword 'Bzhcloud'
               storeFile file('key.keystore')
               storePassword 'Bzhcloud'
               v1SigningEnabled true
               v2SigningEnabled true
           }
       }
   ```

3. 应用名称 strings.xml (/simpleDemo/src/main/res/values/strings.xml)

```
<resources>
    <string name="app_name">你的应用名称</string>
</resources>
```

4. 图标 (/simpleDemo/src/main/res/drawable)
**icon.png** 图标
**push.png** 推送图标
**splash.png(splash.9.png)** 启动图片

5. 资源文件

   4.1  HBuilderX生的本地打包资源文件 (/simpleDemo/src/main/assets/apps/app应用标识)

   4.2 dcloud_control.xml (/simpleDemo/src/main/assets/data/dcloud_control.xml)

   ```
   <hbuilder>
   <apps>
       <app appid="app应用标识" appver=""/>
   </apps>
   </hbuilder>

   ```

   [参考文档](https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android)







