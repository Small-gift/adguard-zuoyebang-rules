# 作业帮 & 快对作业 AdGuard 去广告规则

这是一个专为 K12 教育类 App（如**作业帮**、**快对作业**等）定制的 AdGuard 过滤规则集。旨在拦截应用内的广告请求、日志上传、商城推广以及部分视频 VIP 解析接口，还您一个清爽的学习环境。

## ⚠️ 影响与限制说明（非常重要）

使用本规则在带来清爽体验的同时，也会产生一些不可避免的副作用，请在使用前务必了解：

### 1. 可能会触发风控（未登录无法搜题）
*   **具体表现**：在**未登录**状态下，App 可能会限制核心功能（例如无法正常搜题、提示网络异常或请求失败）。
*   **解决方案**：**登录您的账号即可恢复正常使用。**
*   **原因解释**：本规则屏蔽了部分日志上传接口。服务端风控系统在检测不到正常的设备日志请求时，会判定当前环境存在异常。登录账号后，服务端可以通过您的账号信息完成鉴权，从而解除风控限制。

### 2. VIP 界面仍会显示，但无法开通
*   **具体表现**：在 App 内点击 VIP 或会员中心，界面依然能正常弹出和显示，但点击支付或开通时会失败。
*   **原因解释**：VIP 页面是**内置在 App 安装包中**的，加载时不依赖网络请求，因此 AdGuard 无法拦截界面显示。但是，真正完成开通动作需要向 VIP 服务器（如 `vip.zuoyebang.com` 等）发送请求，由于这些域名已被本规则拦截，导致无法完成开通流程。

## ⚠️ 免责声明
- 使用本规则所产生的一切后果（包括但不限于 App 功能异常、账号封禁等）由使用者自行承担，项目作者不承担任何法律责任。

## ✨ 功能特性
- **去广告**：拦截 `adx`、`vipvideo`、`viprec` 等广告与推荐视频域名。
- **防追踪**：屏蔽 `log`、`selltrack` 等埋点和日志上传接口。
- **精简界面**：拦截 `mall`、`sellgoods`、`sell` 等电商商城推广模块。
- **去活动弹窗**：屏蔽 `activities`、`competition` 等营销活动接口。

## 🚀 如何使用

### 方法一：手动导入（适用于个人定制）
1. 打开 AdGuard 应用。
2. 进入 **设置** -> **内容拦截** -> **用户过滤器**（部分版本叫“自定义过滤器”）。
3. 点击右上角菜单，选择 **导入** 或直接 **添加**。
4. 将下方的规则列表复制并粘贴进去，保存即可。

### 方法二：通过订阅链接
可以使用 Raw 链接直接订阅：
1. 在 AdGuard 中进入 **设置** -> **过滤** -> **过滤器**->**自定义过滤器**。
2. 点击 **添加自定义过滤器** -> **从 URL 添加**。
3. 输入规则 Raw 链接https://raw.githubusercontent.com/Small-gift/adguard-zuoyebang-rules/main/rules.txt
或者使用加速连接
https://gcore.jsdelivr.net/gh/Small-gift/adguard-zuoyebang-rules@main/rules.txt

## 🤝 贡献与反馈
如果您发现新的广告域名或规则失效，欢迎提交 Issues 或 Pull Requests。

## 📄 开源协议
本项目基于 MIT License 协议开源。

这些规则是作者本人自己抓包许久才找到的，可以给本项目做个宣传或者点个Star，感谢你对本项目的支持

## 📋 规则列表（按主域名分组）

```adguard
# bangbangkids.cn
||fengniao.bangbangkids.cn^

# cdnjtzy.com
||fengniaocdn.cdnjtzy.com^
||mall-ssr.cdnjtzy.com^
||sell-3.cdnjtzy.com^
||sell-ssr-1.cdnjtzy.com^
||sell-ssr-2.cdnjtzy.com^
||sell-ssr-3.cdnjtzy.com^
||sell-ssr.cdnjtzy.com^
||sell.cdnjtzy.com^
||sellgoods-z-1.cdnjtzy.com^
||sellgoods-z.cdnjtzy.com^
||vip-3.cdnjtzy.com^
||vipvideo-1.cdnjtzy.com^
||vipvideo-2.cdnjtzy.com^
||vipvideo-3.cdnjtzy.com^
||vipvideo.cdnjtzy.com^
||zyb-vip-1.cdnjtzy.com^
||zyb-vip-2.cdnjtzy.com^
||zyb-vip-3.cdnjtzy.com^
||zyb-vip.cdnjtzy.com^

# fengniaojianzhan.com
||fengniaojianzhan.com^
||selltrack.fengniaojianzhan.com^

# kuaiduizuoye.com
||apivip.kuaiduizuoye.com^
||vip.kuaiduizuoye.com^

# yukeweb.com
||adx.yukeweb.com^

# zhaoqiqslx.com
||app.zhaoqiqslx.com^

# zuoyebang.com
||activities.zuoyebang.com^
||adx.zuoyebang.com^
||apivip.zuoyebang.com^
||competition.zuoyebang.com^
||mall.zuoyebang.com^
||ugc.zuoyebang.com^
||user-vue.zuoyebang.com^
||vip.zuoyebang.com^
||viprec.zuoyebang.com^
```

Ai太好用了你们知道吗
