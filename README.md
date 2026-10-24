# RustDeskX

RustDeskX 是面向 Apple Silicon Mac 的 RustDesk 个人重品牌发行包：

- 应用名称：`RustDeskX`
- Bundle ID：`com.omzcj.rustdeskx`
- 主执行文件：`RustDeskX`
- 架构：仅 `arm64`
- 发行：Developer ID 签名并经 Apple 公证
- 上游版本：RustDesk 1.4.9

本仓库不修改 RustDesk 的远程桌面协议或绕过任何安全机制。构建流程固定校验官方 arm64 DMG 的 SHA-256，然后修改应用包元数据并完整重签。

## 安装

可通过 Homebrew 安装：

```bash
brew tap oh-my-brew/tap
brew install --cask rustdeskx
```

也可以从 Releases 下载 `RustDeskX-<version>-arm64.zip`，解压后拖入“应用程序”。

## 首次配置

1. 在“系统设置 → 隐私与安全性”中为 RustDeskX 开启“屏幕与系统录音”和“辅助功能”；系统提示时再开启“输入监控”。
2. RustDeskX → 设置 → 常规：开启硬件加速。
3. RustDeskX → 设置 → 安全：设置固定密码，并开启“允许 IP 直接访问”。
4. 手机、控制端和被控 Mac 登录同一 Tailscale。
5. 使用 `<Tailscale IP 或 MagicDNS 名称>:21118` 连接。

不需要把 21118 端口暴露到公网。Tailscale 显示 `direct` 时通常延迟最低；`peer-relay` 或 DERP 中继仍可能增加延迟。

更完整的 Tailscale、无人值守与权限说明见 [USAGE.md](USAGE.md)。

## 本地验证构建

```bash
CODE_SIGN_IDENTITY=- Scripts/package-release.sh
```

上述命令生成本地 ad-hoc 验证包，会下载上游 DMG 并写入 `dist/`，不用于正式分发或替换已安装应用。
正式发行使用 `<上游版本>.<修订号>` 标签，例如 `v1.4.9.3`；签名、公证与发布步骤见 [DISTRIBUTION.md](DISTRIBUTION.md)。

## 上游与许可

RustDesk 1.4.9 使用 GNU Affero General Public License v3.0（AGPL-3.0），许可证全文见 [LICENSE](LICENSE)。
对应[上游源码](https://github.com/rustdesk/rustdesk/tree/1.4.9)、重品牌改动及构建入口见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。RustDeskX 与 RustDesk 官方项目没有隶属或背书关系。

助手维护约定见 [AGENTS.md](AGENTS.md)。
