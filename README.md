# Lottie 动画格式转换工具

这是一个浏览器端小工具，用来把 Lottie / Bodymovin 的 `.json` 动画导出为：

- 可循环播放并保留透明背景的 APNG
- 带 Alpha 通道的 ProRes 4444 MOV
- 可循环播放的 GIF
- 打包为 ZIP 的透明 PNG 序列

## 使用方法

1. 在这个文件夹里运行：

   ```bash
   npm start
   ```

2. 打开浏览器访问：

   ```text
   http://127.0.0.1:5173/index.html
   ```

3. 拖入或选择 Lottie JSON 文件，选择格式、尺寸和帧率，然后点击导出。

## 小提示

- MOV 使用 `prores_ks`、Profile 4 和 `yuva444p10le` 编码，保留 Alpha 通道。
- 首次导出 MOV 或 GIF 时需要加载约 31 MB 的浏览器编码器。
- GIF 只支持完全透明或完全不透明；需要平滑半透明边缘时优先使用 MOV、APNG 或 PNG 序列。
- 如果某个 Lottie 引用了外部图片资源，浏览器可能因为跨域限制无法导出。内嵌图片资源的 JSON 最稳。
- 尺寸和帧率越高，导出越清晰，文件也会越大。
