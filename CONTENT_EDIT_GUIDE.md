# 珍珍日上TV 内容维护说明

## 一、后台上传（推荐）

现在首页已经有 **管理后台**（导航栏可打开）。

- 默认密码：`zzrs2026`
- 可上传：视频文件（mp4/webm）、封面图
- 可编辑字段：标题、简介、时长、分区（舞台/综艺/角色/直播）、原链接、站内播放链接、播放类型

### 使用步骤

1. 打开首页右上角 **管理后台**
2. 输入密码进入
3. 填写标题、分区等信息
4. 选择视频文件和封面（或填写播放链接）
5. 点击「保存视频」
6. 页面分区会立即出现新卡片，点击即可在站内播放器播放

> 上传内容保存在当前浏览器的 IndexedDB。  
> 换浏览器、清缓存、换设备后不会自动同步。

---

## 二、手动改默认内容（`index.html`）

如果你想把“默认示例卡片”改成固定内容，可以编辑 `index.html` 里的 `VIDEO_LIBRARY`。

每条视频字段：

- `title`：标题
- `desc`：简介
- `duration`：时长（例如 `04:12`）
- `url`：原站链接（可选）
- `playUrl`：站内播放地址（推荐）
- `playType`：`iframe` / `video` / 留空自动识别
- `cover`：封面图链接

示例：

```js
{
  title: "舞台直拍｜神级卡点",
  desc: "动作干净，镜头表现稳定",
  duration: "03:45",
  url: "https://www.bilibili.com/video/BVxxxx",
  playUrl: "https://player.bilibili.com/player.html?bvid=BVxxxx&page=1",
  playType: "iframe",
  cover: "/images/stage-01.jpg"
}
```

---

## 三、哪些链接能站内播放？

### 推荐（稳定）

- 直链视频：`.mp4` / `.webm`
- 平台 embed 链接：
  - B站：`https://player.bilibili.com/player.html?...`
  - 腾讯：`https://v.qq.com/txp/iframe/player.html?...`
  - 优酷：`https://player.youku.com/embed/...`
  - YouTube：`https://www.youtube.com/embed/...`

### 可能不稳定

- 普通详情页链接（很多平台禁止 iframe 嵌入）

如果不可嵌入，播放器会提示，并可使用「打开原链接」跳转观看。

---

## 四、官群空降截图页

文件：`daily-group.html`

- 顶部和正文按钮都可返回主页
- 截图数据在 `SCREENSHOT_LIBRARY` 中维护
- 字段：`date` / `title` / `desc` / `image`

