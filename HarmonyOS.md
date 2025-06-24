# HarmonyOS学习
## 一、ArkTS工程目录结构
### 1. AppScope
#### app.json5：应用的全局配置信息
https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/app-configuration-file
### 2. entry：HarmonyOS工程模块。（编译构建生成一个HAP包）
#### src
1. main -> ets：用于存放==ArkTS的源码==
	- entryability：为 应用/服务的入口
	- entrybackupability：为 应用提供扩展的备份恢复能力
	- pages：**应用/服务包含的页面**
2. main -> resources：用于存放 应用/服务所用到的**资源文件**。（如：图像、多媒体、字符串等）
资源文件：https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/resource-categories-and-access
3. main -> module.json5：模块配置文件。（主要包含HAP包的配置信息、应用/服务在具体设备上的配置信息以及应用/服务的全局配置信息。）
https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/module-configuration-file
4. build-profile.json5：当前的模块信息 、编译信息配置项，包括buildOption、targets配置等。
5. hvigorfile.ts：模块级编译构建任务脚本。
6. obfuscation-rules.txt：混淆规则文件。
混淆开启后，在使用Release模式进行编译时，会对代码进行编译、混淆及压缩处理，保护代码资产。https://developer.huawei.com/consumer/cn/doc/harmonyos-guides/ide-build-obfuscation
7. oh-package.json5：用来描述包名、版本、入口文件（类型声明文件）和依赖项等信息。
### 3. oh_modules：用于存放三方库依赖信息。
#### build-profile.json5：工程级配置信息。
包括签名signingConfigs、产品配置products等。（其中products中可配置当前运行环境，默认为HarmonyOS）
#### hvigorfile.ts：工程级编译构建任务脚本。
#### oh-package.json5：主要用来描述全局配置。
如：依赖覆盖（overrides）、依赖关系重写（overrideDependencyMap）和参数化配置（parameterFile）等。
