gradle-jery-push
===============

## 一. 介绍

### 提供了简单的仓库工具
```properties
    local.gradle 本地仓库
    java_install_upload.gradle 上传到jcenter
    android_install_upload.gradle android 上传到jcenter
```

## 二、local.gradle 本地仓库的使用

### 1. 在你的gradle.properties增加以下设置
设置gradle.properties
```properties
    GROUP_ID=xxx.xxx.xxx
    VERSION=xxx
```
### 2. 在你的 `build.gradle` 中增加以下设置：

```groovy
    apply from: 'https://raw.github.com/zhangjian31/gradle-jery-push/master/local.gradle'
    
    tasks.withType(GroovyCompile) {
        sourceCompatibility = '1.7'
        targetCompatibility = '1.7'
    }
```
### 3. 发布到本地
```
    $ gradle uploadArchives
```

## 三、java_install_upload.gradle 上传远程仓库的使用
### 1. 在你的 `build.gradle` 中增加以下设置：
```groovy
    classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.6'
    classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
```
```groovy
    apply plugin: 'java'
    apply from: 'https://raw.github.com/zhangjian31/gradle-jery-push/master/java_install_upload.gradle'
```

### 2. 在你的gradle.properties增加以下设置
```properties
    PROJ_SITE_URL=xxx
    PROJ_GIT_URL=xxx
    PROJ_NAME=xxx
    PROJ_DESCRIPTION=xxx
    DEVELOPER_ID=xxx
    DEVELOPER_NAME=xxx
    DEVELOPER_EMAIL=xxx
    GROUP_ID=xxx
    VERSION=x.x.x
```

### 3. 在local.properties中配置bintray帐号信息
```properties
    bintray.apikey=xxxxx
    bintray.user=xxxx
```

### 4. 在.gitignore中记得忽略local.properties，不然你的apikey都泄露了
```
    /local.properties
```

### 5. 发布
```
    $ gradle install
    $ gradle bintrayUpload
```
### 6.添加到Jcenter
```
    登录Bintray网站，找打自己的仓库，点击Add to JCenter，等待审核结果，一般几个小时的时间就会审核通过。
```

## 四、android_install_upload.gradle 上传远程仓库的使用

### 1. 在你的 `build.gradle` 中增加以下设置：
```groovy
    classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.6'
    classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
```
```groovy
    apply plugin: 'com.android.library'
    apply from: 'https://raw.github.com/zhangjian31/gradle-jery-push/master/android_install_upload.gradle'
```

### 2. 在你的gradle.properties增加以下设置
```properties
    PROJ_SITE_URL=xxx
    PROJ_GIT_URL=xxx
    PROJ_NAME=xxx
    PROJ_DESCRIPTION=xxx
    DEVELOPER_ID=xxx
    DEVELOPER_NAME=xxx
    DEVELOPER_EMAIL=xxx
    GROUP_ID=xxx
    VERSION=x.x.x
```

### 3. 在local.properties中配置bintray帐号信息
```properties
    bintray.apikey=xxxxx
    bintray.user=xxxx
```

### 4. 在.gitignore中记得忽略local.properties，不然你的apikey都泄露了
```
    /local.properties
```

### 5. 发布
```
    $ gradle install
    $ gradle bintrayUpload
```
### 6.添加到Jcenter
```
    登录Bintray网站，找打自己的仓库，点击Add to JCenter，等待审核结果，一般几个小时的时间就会审核通过。
```

