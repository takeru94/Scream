#  Scream: Windows平台上一套基于V2Ray和Xray项目的GUI软件
本项目基于[https://github.com/Cenmrev/V2RayW](https://github.com/Cenmrev/V2RayW)，根据自用需求对其UI界面进行了重写。

在此之前一直使用V2RayW项目，但该项目于2019年初便不再维护，于是乎自己动手改造就有了[https://github.com/musva/V2RayW](https://github.com/musva/V2RayW)，相对于V2RayW原始项目添加了必要的功能。随着v2ray-core&xray-core不断更新设置项将会越来越多，V2RayW本就紧凑的界面越发捉襟见肘，于是萌生了对UI界面进行大幅改造的念头。核心代码移植自V2RayW并保留了绝大多数原有功能，静默运行，使用托盘右键满足日常使用。

> **本项目根据自用需求酌情添加新功能。**

## 与[https://github.com/musva/V2RayW](https://github.com/musva/V2RayW)项目有何不同 ？
- 功能
  - 所有协议均需手工配置，vmess/vless/shaodowsocks/trojan协议提供了配置模板
  - 支持vmess/vless/shaodowsocks/trojan协议导入导出
  - 新增修改自定义配置文件现在会自动监测并测试
  - 可配置系统绕行列表
- 界面
  - 支持暗黑模式
- 性能变化
  - 后台静默运行内存占用约20MB，使用界面配置后内存占用约35MB，内存占用较之V2RayW上浮5-10MB

## 适用人群
- 自建节点或有稳定**少量**高质量节点的机场用户
- 较为了解V2Ray配置文件

## 使用说明
- 运行环境
  - .NET Framework 4.6 
- 如何使用
   - 将V2Ray/Xray核心放置在软件目录下的v2ray-core / xray-core文件夹中
   - 运行软件
   - 托盘图标右击-开启核心
- 如何重置
  - 关闭软件，删除软件目录下`settings.json`文件
- 订阅功能
  - 每行一条URL
  - URL行首添加任意字符以达到临时禁用订阅链接目的
- 负载均衡
  - `使用全部`，将使用配置文件中outbound所有节点，选择单个节点或再选`使用全部`即可退出模式
  - `使用部分`，可选多个节点，最少一个，节点处于选中状态时再选即为去除，再选`使用部分`即可退出模式
  - 托盘图标右击-`服务器`-`使用全部/使用部分`
- 路由编辑
  - 路由匹配从上至下请注意规则顺序，非常重要
  - 拒绝，在`tag`填写`decline`
  - 直连，在`tag`填写`direct`
  - 代理，在`tag`填写`main`
  - 当处于负载均衡模式时`main`将会被自动替换为`balance`
  - 当使用单出口/`使用部分`时，支持在路由中定义未被选中的其他出口
- 保留关键字
  - `direct` `direct` `main` `balance`
  - 上述四个关键字因用于路由配置故无法配置为出口标记（tag）
- 绕行
  - 自定义绕过列表为全量配置
  - 右键托盘，配置... - 常规设置 - 绕行
- 自定义配置文件
  - 软件目录下config文件夹放置原生V2Ray/Xray配置文件
  - 新增/修改/删除自定义配置文件无需重启软件
  - 使用托盘右键`服务器`选项切换自定义配置
- 保存配置
  - 当软件正常退出（右键主动退出/系统关机/系统注销）时将会正确保存配置文件
  - 如需主动保存配置，请使用界面`应用配置`
  - `应用配置`将会立即刷新托盘右键菜单选项
- 在软件**关闭状态**下 ，可手动编辑  `settings.json`文件进行参数调整



