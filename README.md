gradle-jery-push
===============

## Usage

### 1. 介绍
提供了简单的仓库工具
    local.gradle
    upload.gradle
    upload_android.gradle

### 2. 在你的gradle.properties增加以下设置
设置gradle.properties

```properties
    GROUP_ID=xxx.xxx.xxx
    ARTIFACT_ID=xxx
    VERSION=xxx
```

### 3. 在local.properties中增加以下设置
```properties
    bintray.apikey=xxxxx
    bintray.user=xxxx
```

The `VERSION_NAME` value is important. 

### 4. 在.gitignore中记得忽略local.properties，不然你的apikey都泄露了

```properties
    /local.properties
```

### 5. 调用 upload.gradle

在你的 `build.gradle` 中增加以下设置：

```groovy
    https://raw.github.com/zhangjian31/android-gradle-output-plugin/master/upload.gradle
```

### 6. 发布

```
    $ gradle install
    $ gradle bintrayUpload
```

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
