# 鲸鱼娘余额伙伴 · Whale Companion

> 常驻 DeepSeek Harness 右下角的鲸鱼娘挂件：随时看一眼余额，顺便换张表情。

[English](README.en.md) · [更新日志](CHANGELOG.md) · [参与贡献](CONTRIBUTING.md)

![version](https://img.shields.io/badge/version-1.3.0-4FD1C5)
![license](https://img.shields.io/badge/license-MIT-blue)
![platform](https://img.shields.io/badge/platform-DeepSeek%20Harness-1E3A5F)
![art](https://img.shields.io/badge/art-fan--made%20%C2%B7%20non--commercial-FFB3C3)

![十六张鲸鱼娘表情](assets/gallery.webp)

## 亮点

- **全局常驻** — 挂在 Harness 的 `shell.overlay` 浮层上，切换会话、新建会话、打开其它面板都不消失；浮层本身点击穿透，只占右下角一块。
- **实时余额** — 每 30 秒自动读一次 DeepSeek 账户钱包，页面重新可见时立即刷新，点金额也能立刻刷新。
- **大口径显示** — 204px 方图 + 38px 余额数字，竖向卡片只占 234px 宽，把右侧空间往上用，不挤输入框。
- **十六张表情** — 左键换一张、`Shift + 左键`随机换；支持「自动·顺序 / 自动·随机 / 手动」三种轮换方式，悬停时自动轮换暂停。
- **零依赖** — 纯 JavaScript，无需构建；图片以 WebP data URI 内嵌，断网也能显示。
- **不碰凭证** — 插件不读取、不保存任何 token，余额请求由 Harness 自身的账户通道完成。

## 界面

```
        ┌──────────────────┐
        │                  │   204 × 204 圆角方图
        │     鲸鱼娘        │   左键换一张 · Shift+左键随机
        │                  │
        └──────────────────┘
        ┌──────────────────┐
        │ 余额              │   23px 标签
        │ ¥0.00            │   38px 数字
        │ + 赠送 ¥4.65      │   22px 绿色（有赠送时出现）
        │ ‹  自动·顺序  ›   │   22px 控制条（悬停高亮）
        └──────────────────┘
```

- 充值余额与赠送额度分开显示，口径与官方账户页一致；赠送额度只显示正数。
- 未登录账户（例如只用 API Key）显示「登录后就能看到余额啦」。
- 读取失败时保留上一次的金额并整体变淡，不会闪成 0。
- 金额过长（>9 字符）会自动降一档字号，防止溢出卡片。

## 安装

需要已安装 DeepSeek Harness，并且账户功能可用（Windows / macOS 桌面端或浏览器里的 Web 界面均可）。

**方式一：图形界面（推荐）**

1. 下载 [Releases](../../releases) 里的 `whale-companion-1.3.0.zip`，解压到一个固定目录，例如 `C:\Users\你\Documents\whale-companion`；
2. 打开侧边栏 **插件 → 添加插件**（或箭头里的 **安装第三方插件**）；
3. 粘贴解压后目录的**绝对路径**，或本仓库的 Git 地址，确认信任提示后安装；
4. 页面没变化就刷新一次。

**方式二：让 Agent 装**

> 帮我安装本地插件包 `C:\Users\你\Documents\whale-companion`

Agent 会调用 `plugin_manager` 的 `install_bundle`；返回 `application: applied` 即已生效。

**方式三：npm / tarball**

```bash
pnpm add /path/to/whale-companion-1.3.0.tgz
```

也可以把 `package.json` 的 `name` 改成自己的 scope 后发布到 npm，朋友在「添加插件」里直接填包名。

**卸载**：设置 → 插件 → 停用或移除「鲸鱼娘余额伙伴」，或让 Agent 执行 `remove_bundle`（目标 `@local/whale-companion`）。

## 使用

| 操作 | 效果 |
| --- | --- |
| 左键点击图片 | 下一张表情（并重置自动轮换计时） |
| `Shift` + 左键 | 随机换一张 |
| 悬停卡片 | 出现 `‹` `›` 与模式按钮，自动轮换暂停 |
| 点模式按钮 | 自动·顺序（60 秒）→ 自动·随机 → 手动 |
| 点余额数字 | 立即刷新余额 |

## 余额口径

余额来自已登录的 DeepSeek 账户，包含两类钱包：

- **充值余额**：主显示行，按币种格式化为两位小数；
- **赠送额度**：绿色 `+ 赠送` 行，仅在存在正数赠送时出现，与充值余额分开计。

两者都不代表「本次会话花费」；会话用量请查看 Harness 自带的用量提示。

## 图片与版权

十六张图全部来自公开的粉丝表情包合集 [deepseek-chan-meme-pack](https://github.com/the-beating-light-of-the-nail/deepseek-chan-meme-pack)（梗鲸 GengJing）：

- 采集规则：**所有方图**直接入选；**非方图**仅在长宽比 ≤ 1:1.2 时入选并居中裁剪。
- 入选：`007 010 022 035 037 040 044 050 052 070 071 077 081 083 085 123`；
- 因比例超限被排除：`056`(1.40)、`058`(1.33)、`087`(1.40)、`097`(1.33)。

角色「蓝色大肥鱼 / 鲸鱼娘 / DeepSeek娘」与原始画作版权归原作者及社区作者所有。本插件仅作个人、非商业用途，不主张任何美术权利；商业使用请先取得原作者许可。完整声明与下架渠道见 [NOTICE.md](NOTICE.md)。

## 常见问题

**为什么只显示 ¥0.00 和赠送额度？**
充值余额确实是 0，赠送额度是独立钱包；官方账户页也是分两行展示的。

**为什么看不到鲸鱼娘？**
确认插件已启用、且当前页面已刷新；如果你的界面没有账户登录，插件仍会显示登录提示而不是余额。

**会不会把我的余额或凭证上传到别处？**
不会。余额请求走 Harness 的账户服务，插件只拿到钱包金额与币种；它不读取 token，也没有任何第三方上报。

**能换成自己的图吗？**
可以，编辑 `client.js` 顶部 `ARTS` 数组的 data URI 即可；图片建议 1:1、≥256px、WebP 压缩。

**会不会挡住界面？**
只占右下角 234 × 约 400 的一列，浮层层级低于弹窗；打开右侧边栏面板时可能覆盖它底部一小块。

## 开发

```text
whale-companion/
├─ index.js            # Host 半：空 apply（渲染全在客户端）
├─ client.js           # Client 半：SVG 之外的 UI、轮换、余额读取（图片内嵌）
├─ cordis.patch.yml    # bundle 插入的插件行
├─ assets/             # 插件图标 + 16 张一览图
├─ locale/             # 插件管理页的标题与描述
├─ docs/               # 发布文案、仓库设置（不随插件安装）
└─ package.json        # dsh.bundle / dsh.client 声明
```

- 没有构建步骤：改完 `client.js` 重新安装一次（`remove_bundle` → `install_bundle`）再刷新页面即可，客户端 bundle 按插件行缓存。
- 只使用主题 token（`--dsw-alias-*`）与原生 React，不依赖 Harness 的 Client 包。
- 详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 更新日志

见 [CHANGELOG.md](CHANGELOG.md)。最近：**1.3.0** — 界面 1.5 倍、字体 2 倍、16 张表情、圆角方图。

## 许可

- 代码：[MIT](LICENSE)
- 美术素材：版权归原作者，非商业粉丝使用，**不包含在 MIT 授权内**（见 [NOTICE.md](NOTICE.md)）

---

<sub>本项目是社区插件，与 DeepSeek 官方无隶属关系。DeepSeek Harness 的插件机制见其官方文档。</sub>
