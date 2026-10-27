# quantumultx-config

Quantumult X 配置与分流规则（公开仓库）。只放公开规则与配置模板，**不含任何个人订阅链接**。

## 文件

- `QuantumultX.conf`：整套配置（策略组、DNS、远程分流规则、本地兜底规则、MITM 示例）
- `rules/custom-direct.list`：自定义直连规则（想直连的域名/IP 写这里）
- `rules/custom-proxy.list`：自定义代理规则（想走代理的域名/IP 写这里）

## 怎么用

### 方式一：整套配置导入（推荐）

远程地址：

```
https://raw.githubusercontent.com/yyloveyouu/quantumultx-config/main/QuantumultX.conf
```

1. 先在 Quantumult X 里备份现在的配置（下载配置会整体覆盖）。
2. QX → 设置 → 下载配置，粘贴上面的地址，确认。
3. 导入后，在 QX 本地添加自己的订阅（远程节点资源）。**订阅链接不要写进仓库的任何文件**——本仓库是公开的，任何人可见。
4. 需要 MITM 时，在 QX 本地生成证书并到 iOS 系统设置里信任；配置文件只给了常用 hostname 示例。

### 方式二：只加分流规则

把 `QuantumultX.conf` 里 `[filter_remote]` 段的每一行链接，逐个添加为 QX 的远程分流规则，策略按各行的 `force-policy` 设置。

## 规则来源与更新

- 主规则集：[blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) 的 QuantumultX 规则（广告拦截轻量版、国内直连、全球代理、国内/全球流媒体、Netflix、YouTube、Telegram），QX 每 2 天自动拉取更新。
- 自定义规则在本仓库 `rules/` 下维护，改完提交后在 QX 端更新资源即可同步。

## 注意

- 本仓库为公开仓库。不要提交订阅链接、节点信息、账号密码等任何私人内容。
