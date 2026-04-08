# 珍珍日上TV 内容替换说明

## 1) 视频链接是不是哪里都行？

不完全是。要实现“在本站内播放 + 可切视频”，建议优先使用 **可嵌入链接**：

- B站：`https://player.bilibili.com/player.html?...`
- 腾讯视频：`https://v.qq.com/txp/iframe/player.html?...`
- 优酷：`https://player.youku.com/embed/...`
- YouTube：`https://www.youtube.com/embed/...`

> 注意：普通网页详情链接（如 `https://www.bilibili.com/video/BV...`）通常不能直接在 iframe 内稳定播放。  
> 推荐填平台提供的“分享嵌入代码”里的 iframe `src` 链接。

---

## 2) 替换首页视频（index.html）

打开 `index.html`，找到脚本中的 `VIDEO_LIBRARY`：

- `stage`：舞台安利
- `show`：综艺安利
- `role`：角色安利
- `live`：直播回放

每条视频字段：

- `title`：标题
- `desc`：简介
- `duration`：时长（如 `04:12`）
- `embedUrl`：站内播放器使用的嵌入链接（最重要）
- `originUrl`：源站链接（“源站打开”按钮使用）
- `cover`：封面图链接（可留空）

示例：

```js
{
  title: "舞台直拍｜神级卡点",
  desc: "动作和镜头表现都很稳",
  duration: "03:45",
  embedUrl: "https://player.bilibili.com/player.html?bvid=BVxxxx&page=1",
  originUrl: "https://www.bilibili.com/video/BVxxxx",
  cover: "https://your-cdn.com/szn-stage-1.jpg"
}
```

---

## 3) 官群空降截图（daily-group.html）

打开 `daily-group.html`，找到 `SCREENSHOT_LIBRARY`。

字段：

- `date`：日期
- `title`：标题
- `desc`：说明
- `image`：图片链接

示例：

```js
{
  date: "2026-04-08",
  title: "晚间空降互动",
  desc: "聊了舞台准备和近期安排。",
  image: "/images/kongjiang-20260408.jpg"
}
```

---

## 4) 现在的播放逻辑

- 点击任一视频卡片，会在首页顶部播放器区“站内切换并播放”
- 播放器右上角有“源站打开”按钮
- 若 `embedUrl` 为空，会提示先补充嵌入链接

