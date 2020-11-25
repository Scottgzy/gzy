# 北京邮电大学沙河校区健身房预约脚本

该脚本用于预约北京邮电大学沙河校区健身房，引用/使用请遵循 GPLv3 开源协议。

## 依赖

-   Python 3.8.5 （开发环境）
-   requests：发送 HTTP 请求
-   BeautifulSoup4：解析 html 页面
-   ExecJs：用于执行页面上的 JavaScript 脚本
-   PyCryptoDome：AES 加密

## 特性

-   高可用性，在大部分环境下均可部署使用
-   高可拓展性，方便二次开发
-   使用 Server 酱进行消息推送

## 更新日志 Changelog

**2020/11/25** 添加 Server 酱提示功能，添加概率启动功能（用于防止被服务器 ban 掉）

## 部署

可以使用校内或者校外的服务器进行部署，具体流程：

1. `git clone git@github.com:Hyiker/bupt-gym-reserve.git` 将代码仓库克隆到本地或者下载 zip 包
2. `cd bupt-gym-reserve && pip3 install -r requirements.txt`
3. `python3 main.py -u 信息门户用户名 -p 信息门户登录密码 -k server酱的SCKEY`
4. （可选）将脚本执行命令添加到`crontab`中

## 参数说明

|      命令行参数      |                                          说明                                          |
| :------------------: | :------------------------------------------------------------------------------------: |
|    --username -u     |                                          学号                                          |
|    --password -p     |                                      信息门户密码                                      |
| --sckey -k （可选）  |                    server 酱提供的 SCKEY，如果不需要推送通知则留空                     |
| --chance -c （可选） | 输入一个整数 k，如果填写，则脚本只有 k% 的概率会实际运行，随机变量为离散的，默认为 100 |

这是一个用于演示的 example

```bash
python3 main.py -u 2019114514 -p 1919810
```

## 免责声明

该脚本仅用于北京邮电大学校内学生交流学习使用，遵循 GPLv3 开源协议，本人不对脚本使用产生的后果负任何责任