# Changelog

## v6.6.0 (2026-08-20) — 俄语本地化 / Russian Localization

### 🌐 国际化 / Internationalization

- **新增俄语完整本地化支持** — 添加 `ru` 语言到语言选择器，自动检测 `ru`, `ru-RU`, `ru-BY`, `ru-KZ`, `ru-KG` 区域设置
- **俄语翻译全覆盖** — 625/625 前端 i18n 翻译键 + 26/26 HA 配置流翻译键，感谢 @BrainDeLook 的贡献
- **新增俄语 README** — 完整的俄语文档，包含安装、配置、使用说明和更新日志
- **响应式布局修复** — 语言选择和设置区域改用响应式网格布局，解决长翻译标签溢出问题
- **语言选择器修复** — 修复页面重载后语言选择器显示错误的问题，动态语言选项现在会正确选择有效语言

### PR [#27](https://github.com/C3H3-AI/hacs-vision/pull/27)

## v6.5.5 (2026-08-02) — XSS 安全修复 / XSS Security Fix

### 🛡️ 安全 (Security)

- **修复 README XSS 漏洞 (V-003, HIGH)** — 后端获取 GitHub 渲染的 README HTML 后经过 DOMPurify 消毒再返回前端，防止恶意仓库作者注入脚本。感谢 @anupamme 的贡献
- **Fixed README XSS vulnerability (V-003, HIGH)** — Backend now sanitizes GitHub's rendered README HTML via DOMPurify before returning to the frontend, preventing malicious repository authors from injecting scripts. Thanks to @anupamme for the contribution

## v6.4.3 (2026-07-16) — 服务补全 & 可移植性优化

### ✨ 改进

- **auto_update 服务定义补全** — 补全 `auto_update_start` / `auto_update_stop` / `auto_update_trigger` / `auto_update_reload_settings` 四个服务，开发者工具中现可看到名称与描述
- **截图地址生成优化** — 截图 URL 兜底逻辑改为按 HA 配置的 external/internal URL 动态派生基地址，提升跨环境可移植性
- **降低 HACS 内部耦合** — 部分内部调用由 `self._hacs.hass` 改为 `self.hass`，减少私有 API 依赖

### 🧹 清理

- **移除未使用的 Gitee 模块** — 删除从未被引用的 `api_mixins/gitee.py`，精简代码体积
- **清理冗余翻译** — 移除 `zh-Hans.json` 中无对应 OptionsFlow 的 `options` 段
