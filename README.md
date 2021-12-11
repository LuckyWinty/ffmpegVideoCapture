# ffmpegVideoCapture
ffmpeg 的 wasm 版本，一个为 umd 格式的 npm 包，用于快速测试前端截帧

### 按照

```js
npm i ffmpegvideocapture
```
### 使用
```js
import ffmpegVideoCapture from 'ffmpegvideocapture'

const getVideoFrameByFfmpeg = async (file) => {
  return await new Promise((resolve) => {
    ffmpegVideoCapture.capture(file, 1000, async (dataURL, imageInfo) => {
      //dataURL 封面，格式为 base64
      //imageInfo 图片信息
      console.log('----imageInfo', dataURL, imageInfo)
      resolve({dataURL, imageInfo})
    })
  })
}
```