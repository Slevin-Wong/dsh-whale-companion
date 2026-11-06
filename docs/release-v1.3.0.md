# v1.3.0 — 1.5× 界面、2× 字体、16 张表情

这次把挂件整体放大了一档，并把可选形象扩充到 16 张（全部来自表情包仓库，按“方图优先、近方图自动裁剪”的规则采集）。

## 亮点

- **更大**：204px 圆角方图 + 38px 余额数字，卡片宽 234px，竖向排列不挤输入框。
- **16 张表情**：左键换一张、`Shift+左键`随机；自动·顺序（60 秒）/ 自动·随机 / 手动三档，悬停暂停。
- **余额口径不变**：充值余额 + 赠送额度分列显示，30 秒自动刷新，点金额立即刷新。
- **图片全部内嵌**：WebP data URI，断网可用；长金额自动降一档字号防溢出。
- **零依赖、无需构建**：纯 JavaScript，装完即用。

## 安装

1. 下载下方 `whale-companion-1.3.0.zip` 并解压到固定目录；
2. DeepSeek Harness → 侧边栏 **插件 → 添加插件** → 粘贴该目录绝对路径（或直接把路径交给 Agent 安装）；
3. 刷新页面。

也可以安装 `whale-companion-1.3.0.tgz`（npm 包格式）。

## 附件与校验

| 文件 | 大小 | SHA-256 |
| --- | --- | --- |
| `whale-companion-1.3.0.zip` | 340,679 B | `AAC4EE39EEEFA313346C218B27CFEDFC98070E0AC09CED8A34E1E2341A527462` |
| `whale-companion-1.3.0.tgz` | 336,326 B | `32F1149CDB5479F3DD4D4D4082C4D73025EA8879E1A7D0D5B5B0762059CE8897` |

Windows 校验：

```powershell
Get-FileHash .\whale-companion-1.3.0.zip -Algorithm SHA256
```

## 需要注意

- 采集规则：所有方图入选；非方图仅在长宽比 ≤ 1:1.2 时入选并居中裁剪。因此 `056`、`058`、`087`、`097` 被排除，**上一版默认的“得加钱”097 不再出现在轮换里**，插件图标也换成了 `007`。
- 需要已登录的 DeepSeek 账户才能看到余额；只用 API Key 时显示登录提示。
- 图片为同人素材，非商业使用；角色版权归原作者（详见仓库 `NOTICE.md`）。

## English

**v1.3.0 — 1.5× UI, 2× type, sixteen expressions.** The widget is scaled up (204px portrait, 38px balance figure, 234px card) and now rotates through sixteen previews from the DeepSeek-chan meme pack: every square image plus one near-square crop (ratio ≤ 1.2). Install the zip via Plugins → Add plugin, or the tarball through npm. Requires a signed-in DeepSeek account; the artwork is fan-made and non-commercial.
