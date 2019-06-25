# 安装
  
由于我的电脑系统是的deepin的,所以其他系统的安装方法请根据我提供的链接自行安装,如果你心情好可以帮我完善下其他系统的安装流程

## lua
 > 参考地址:https://www.lua.org/download.html

### linux

```shell
curl -R -O http://www.lua.org/ftp/lua-5.3.5.tar.gz
tar zxf lua-5.3.5.tar.gz
cd lua-5.3.5
make linux test
```
### 设置环境变量
 
>如果你跟我一样使用了zsh那么需要添加lua环境

```shell
  vim .zshrc
  export LUA_HOME=安装目录
  export PATH=$LUA_HOME/src:$PATH
```
完事后执行: `source .zshrc`

### 验证

```shell
➜  ~ lua -v
Lua 5.3.5  Copyright (C) 1994-2018 Lua.org, PUC-Rio
```

#### 可能遇到的问题

  * lua.c:80:31: fatal error: readline/readline.h: 没有那个文件或目录

    ```shell
     # 出现这个问题是缺少依赖库
     sudo apt-get install libreadline-dev
    ```
  完事后继续执行:`make linux test`  