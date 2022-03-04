# 主题样式 #  

## 引用 ##  

### 设置 npm scope ###  

一般的 `npm` 或 `yarn` 会首先使用 `.mpmrc` 文件配置中的 `scope` 配置  
无 `.npmrc` 文件时使用 `npm` 配置中的 `scope` 配置  
以下配置中 有其中之一即可  

1. 设置 `npm config`  
    ```shell
    npm config set @insgeek:registry http://nexus.insgeek.cn/repository/npm-host/
    ```
    此时 `npm config list` 中会有如下配置  
    ```shell
    @insgeek:registry = "http://nexus.insgeek.cn/repository/npm-host/"
    ```

2. 项目中配置 `.npmrc`  
    在 `.npmrc` 文件中添加如下配置  
    ```shell
    @insgeek:registry = "http://nexus.insgeek.cn/repository/npm-host/"
    ```

### 引用 ###  

设置 `scope` 后即可引入  

1. 引入  
    项目中执行 `yarn add @insgeek/theme` 引入此工具类  

2. 引用  
    本样式库文件必须前置于 `element-ui` 样式文件  
    ```scss
    @import "@insgeek/theme/theme/quotation.scss";
    @import "@insgeek/theme/style/index.scss";
    // 本样式库文件必须前置于 element-ui 样式文件
    @import "element-ui/packages/theme-chalk/src/index";
    ```

3. 按需加载  
    暂无  

## 测试 ##  

需要通过 `yarn link` 链接入业务项目进行测试  

## 打包发版 ##  

1. 登录私有 `npm`  
    此步骤在未登录时只需执行一次  
    执行 `yarn login http://nexus.insgeek.cn/repository/npm-host/` 登录本地源  
    `npm username` 为 `insgeek` 此条为必须  
    `npm email` 为 `wei.chen@insgeek.com` 此条为必须  

2. 发板  
    此样式代码库无编译  
    根目录执行 `yarn publish` 此时需要输入 `wei.chen@insgeek.com` 账号密码 详情咨询大喜哥(wei.chen@insgeek.com)  
    确认发布版本后即可  

    `http://nexus.insgeek.cn/#browse/search/npm` 搜索 insgeek scope 可查看历代版本发布包  
