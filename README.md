gradle-jery-push
===============

# Usage

## 一. 介绍

提供了简单的仓库工具
    local.gradle 本地仓库
    upload.gradle 上传到jcenter
    upload_android.gradle android 上传到jcenter

##二、local.gradle 本地仓库的使用
### 1. 在你的gradle.properties增加以下设置
设置gradle.properties

```properties
    GROUP_ID=xxx.xxx.xxx
    ARTIFACT_ID=xxx
    VERSION=xxx
```
##三、upload.gradle 上传远程仓库的使用
### 1. 在你的gradle.properties增加以下设置
```properties
    GROUP_ID=xxx.xxx.xxx
    ARTIFACT_ID=xxx
    VERSION=xxx
```

### 2. 在local.properties中增加以下设置
```properties
    bintray.apikey=xxxxx
    bintray.user=xxxx
```

### 3. 在local.properties中增加以下设置
```properties
    bintray.apikey=xxxxx
    bintray.user=xxxx
```

### 4. 在.gitignore中记得忽略local.properties，不然你的apikey都泄露了
```properties
    /local.properties
```

### 5. 在你的 `build.gradle` 中增加以下设置：
```groovy
    apply from: 'https://raw.github.com/zhangjian31/gradle-jery-push/master/upload.gradle'
```

### 6. 发布
```
    $ gradle install
    $ gradle bintrayUpload
```

##四、upload_android.gradle 上传远程仓库的使用







## License

    Copyright 2013 Chris Banes

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
