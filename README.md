# uniapp-build-packges

uniapp本地打包

## 基础环境
1. 依赖: JRE, gradle
2. 软件: Android Studio

## 文件
1. Androidmanifest.xml (/simpleDemo/src/main/AndroidManifest.xml)
**android:value** appKey字符串
```
<meta-data
            android:name="dcloud_appkey"
            android:value="你的appKey" />
```
2. build.gradle (/simpleDemo/build.gradle)
名称 值 类型
--- --- ---|
applicationId 包名 字符串
versionCode   主版本 整数
versionName   版本号 字符串
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





