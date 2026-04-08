# 珍珍日上TV 内容替换说明

## 1) 替换首页视频（index.html）

打开 `index.html`，找到脚本里的 `VIDEO_LIBRARY`：

- `stage`：舞台安利
- `show`：综艺安利
- `role`：角色安利
- `live`：直播回放

每条视频可改字段：

- `title`：标题
- `desc`：简介
- `duration`：时长（如 `04:12`）
- `url`：点击跳转链接（B站/微博/腾讯视频/优酷等）
- `cover`：封面图链接（可留空）

示例：

```js
{
  title: "舞台直拍｜神级卡点",
  desc: "动作和镜头表现都很稳",
  duration: "03:45",
  url: "https://www.bilibili.com/video/BVxxxx",
  cover: "https://your-cdn.com/szn-stage-1.jpg"
}
```

## 2) 替换官群空降截图（daily-group.html）

打开 `daily-group.html`，找到脚本里的 `SCREENSHOT_LIBRARY`。

每条截图可改字段：

- `date`：日期
- `title`：标题
- `desc`：描述
- `image`：截图链接（可留空）

示例：

```js
{
  date: "2026-04-08",
  title: "晚间空降互动",
  desc: "聊了舞台准备和近期安排。",
  image: "/images/kongjiang-20260408.jpg"
}
```

## 3) 图片建议

- 封面比例建议：`16:9`
- 官群截图比例建议：`9:16` 或手机长图
- 图片可放仓库目录（如 `/images/...`），或使用图床/CDN 链接

