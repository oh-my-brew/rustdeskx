# RustDeskX 维护约定

先读 `README.md`、`DISTRIBUTION.md`、`THIRD_PARTY_NOTICES.md` 和 `Config/upstream.env`，检查Git状态并保留并行修改；不reset、clean、stash、强推或擅自切分支。

- 本仓库只对固定上游 arm64 应用包重品牌、重签和打包。不得把它描述为自行构建RustDesk源码或修改远控协议。
- 上游版本、Build、DMG SHA-256和本项目修订号统一在 `Config/upstream.env` 维护；变更时核对官方资产和摘要，不绕过下载校验。
- 保持 Bundle ID `com.omzcj.rustdeskx`、Team ID `566UG6DQ7E`、arm64、Developer ID、公证与上游版权信息。
- 许可证为AGPL-3.0，全文在 `LICENSE`；对应上游源码、包装源码和分发说明与版本同步。发布说明需带准确源码入口，不把仓库的通用Source code附件当成上游完整源码。
- 文档修改仅核对链接、配置一致性和 `git diff --check`。脚本修改按范围运行 `bash -n Scripts/*.sh`、Ruby语法及现有CI中的隔离检查。
- `Scripts/package-release.sh` 会下载DMG、挂载并写入产物，只有任务需要构建时才运行；普通验证不启动应用、不连接真实远程设备、不修改权限或关闭其他会话。
- 发行遵循 `DISTRIBUTION.md` 与当前工作流，Match只读；不回显或提交密码、P8/P12、profile、私钥或日志。不为文档修订创建标签、公证、发布或安装。
- 使用说明放README，发行步骤放DISTRIBUTION，交付说明实际检查、资产和未验证项。产品Release、Tap更新与设备安装分别核实。
