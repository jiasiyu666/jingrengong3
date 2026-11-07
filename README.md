# 景仁宫 · 岂容你放肆

一个古风自律番茄钟：择道、燃香、大臣归心、登基。

## 分心守望（新）

燃香开始时，程序会先弹出「守望允准」卡，取得你的许可后才开始计时：

- **离开监视**：燃香期间切走页面、切到别的窗口超过阈值（默认 2 秒），立即响铃并在系统通知里催你回来；回到页面即弹出鞭笞界面。
- **截屏留证（可选）**：勾选后浏览器会弹出共享屏幕授权，只在命中分心时于本机截一张图作为罪证，不上传。
- **设置**：右侧「数据」页可随时开关守望、修改判定阈值、开启/关闭截屏留证。

浏览器沙箱无法读取你具体打开了哪个软件，也无法把窗口置顶到其他应用之上。需要**真正识别抖音 / 快手 / 哔哩哔哩并把鞭笞窗口强制置顶**，请使用配套的 Windows 桌面版（见 `jingrengong-desktop.zip` 内的说明）。

## 文件说明

| 文件 | 说明 |
| --- | --- |
| `index.html` | 主站版本。单文件，1.1MB，图片全部内联，念白使用浏览器中文语音合成 |
| `full.html` | 完整配音版，9.4MB，88 条预生成配音全部内联，加载稍慢，建议用电脑浏览器打开 |
| `.nojekyll` | 告诉 GitHub Pages 不要用 Jekyll 处理，可避免部分文件被忽略 |

两个文件都是**完全独立的单文件**：不依赖 `assets/`、不依赖任何服务器接口，下载后可离线运行。

## 上传到 GitHub 并生成网址

### 方式一：网页上传（不用装 Git）

1. 登录 GitHub，点右上角 `+` → `New repository`
2. 仓库名填 `jingrengong`，可见性选 `Public`，点 `Create repository`
3. 点 `uploading an existing file`（或 `Add file` → `Upload files`）
4. 把本目录下的 `index.html`、`full.html`、`.nojekyll` 一起拖进去
5. 下方点 `Commit changes`
6. 进入仓库 `Settings` → 左侧 `Pages`
7. `Source` 选 `Deploy from a branch`，分支选 `main`、目录选 `/ (root)`，点 `Save`
8. 等待约 1 分钟，页面顶部会出现网址：
   `https://你的用户名.github.io/jingrengong/`
9. 打开该网址即可；`https://你的用户名.github.io/jingrengong/full.html` 是完整配音版

### 方式二：命令行

```bash
cd github-pages
git init
git add .
git commit -m "景仁宫番茄钟"
git branch -M main
git remote add origin https://github.com/你的用户名/jingrengong.git
git push -u origin main
```

推送后同样到 `Settings` → `Pages` 开启即可。

## 使用说明

1. 打开页面，先点「皇子道」或「女官道」——这一步同时解锁浏览器音频播放权限
2. 开头剧情逐句点屏幕推进
3. 点「燃香」开始计时，镜头推到香上，香随倒计时燃烧
4. 中途点「作废」会触发鞭笞动画，本炷香作废
5. 四炷香为一班，班满一位大臣归心；满 20 位自动进入登基剧情，可选「勤政 / 享乐」
6. 设置页可调香长、开关语音、导入自己的音频作为闹钟铃声

## 常见问题

**打开后没有声音？**
浏览器禁止自动播放，必须先点一下页面（择道按钮）。仍无声音时，确认 `设置 → 剧情配音` 已开启，并使用 Chrome / Edge（中文语音最全）。系统没有任何中文语音时，`full.html` 仍可正常发声。

**页面空白？**
确认文件名是 `index.html`（不是 `index.html.txt`）。Windows 可在文件夹选项里开启「显示文件扩展名」检查。

**手机能看吗？**
可以，但配音与动画在小屏上体验一般，建议电脑使用。

**数据存在哪？**
存在浏览器 localStorage，换浏览器或清缓存会重置，不上传到服务器。

**Pages 打开是 404？**
等 1~2 分钟再刷新；确认分支是 `main`、目录是 `/ (root)`；确认仓库是 Public。

## 其他版本

同目录的 `mp-user`、`mp-dev` 是微信小程序工程（需用微信开发者工具导入），网页版与其功能一致。
