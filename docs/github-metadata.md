# GitHub 仓库文案与设置

仓库建好后，把下面这些直接复制到对应位置即可。

## 仓库名

推荐：`dsh-whale-companion`

备选：

- `whale-companion-dsh`
- `deepseek-harness-whale-companion`
- `dsh-balance-whale`

> 名字尽量带 `dsh` 或 `deepseek-harness`，方便同好搜索；不要用 `deepseek` 开头让人误以为是官方仓库。

## About（仓库右上角描述）

英文（推荐，约 115 字符）：

```text
A whale-girl companion for DeepSeek Harness: shows your account balance in real time and rotates through 16 expressions.
```

中文（如果仓库主要面向中文用户）：

```text
常驻 DeepSeek Harness 右下角的鲸鱼娘挂件：实时显示账户余额，可在 16 张表情间自动或手动切换。
```

Website 留空；如果以后有安装说明页再填。

## Topics（最多 20 个，小写、连字符）

```text
deepseek
deepseek-harness
dsh-plugin
dsh
plugin
whale-chan
whale
desktop-widget
balance
status-bar
meme
fan-art
javascript
cordis
```

## README 标题（H1）

当前：

```markdown
# 鲸鱼娘余额伙伴 · Whale Companion
```

备选风格：

- `# 鲸鱼娘余额伙伴`（更短，中文优先）
- `# Whale Companion · 鲸鱼娘余额伙伴`（英文优先，适合发到国际社区）
- `# 鲸鱼娘余额伙伴 — DeepSeek Harness 余额挂件`

## 社交预览（Settings → Social preview）

上传 `assets/gallery.webp`（558×558，正方形），或裁成 1280×640 的横幅再加一行标题：

```text
鲸鱼娘余额伙伴 · 16 张表情 · 实时余额 · DeepSeek Harness 插件
```

## Release 文案

标题格式：`v1.3.0 — 1.5× 界面、2× 字体、16 张表情`

发布说明正文直接用 `docs/release-v1.3.0.md`，并把 `whale-companion-1.3.0.zip` 与 `.tgz` 作为附件上传。

## 首次发布清单

1. GitHub 新建空仓库（不要勾 README / .gitignore / license）；
2. 本地执行：

   ```powershell
   cd "C:\Users\clouder\Documents\deepseek-harness\default-workspace\whale-companion"
   git remote add origin https://github.com/<你的账号>/dsh-whale-companion.git
   git push -u origin main
   ```

3. 仓库 → Settings → 填 About 和 Topics；
4. Releases → Draft a new release → tag `v1.3.0` → 粘贴发布说明 → 上传 zip/tgz；
5. 可选：把 Release 置顶（Pin），并在 README 顶部加下载徽章链接。

## 置顶/推荐用语（用于个人主页或群公告）

```text
[插件] 鲸鱼娘余额伙伴 for DeepSeek Harness — 右下角常驻，实时看余额，16 张表情可换。MIT 代码，非商用同人图。
```
