# Quantumult X 规则配置完全指南

Quantumult X 是 iOS 上功能最全的代理工具，本教程介绍进阶规则配置。

## 基础分流策略

```ini
[policy]
static=香港节点, server-tag=香港
static=自动选择, static-server=香港节点|日本节点|美国节点, policy-params=urltest-interval=300
```

## 分流规则

```ini
[filter]
# 广告拦截
HOST-SUFFIX,doubleclick.net,REJECT

# 社交媒体
HOST-SUFFIX,facebook.com,自动选择

# 国内直连
GEOIP,CN,DIRECT

# 默认
FINAL,自动选择
```

## 节点分组

```ini
[server_local]
us-example-hk01=ss, server-address, port, encrypt-method, password
us-example-hk02=ss, server-address, port, encrypt-method, password
```

## Rewrite 重写规则

### 广告拦截

```ini
[rewrite]
^https?://api\.example\.com/ad reject-dict-matched
```

### 解锁流媒体

```ini
^https?://www\.netflix\.com host-suffix, netflix.com, 你的节点
```

---

推荐工具：

- [Clash for Windows](https://clashforwindows.site/)
- [ClashMI](https://clashmi.site/)
- [FlClash](https://flclash.us/)
