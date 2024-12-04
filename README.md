# 生日祝福网页

这是一个基于 Canvas 的粒子动画生日祝福网页。包含密码验证、粒子动画、音乐播放等功能。

## 主要特点

- 密码验证页面
- 粒子动画文字效果
- 渐变背景
- 星星特效
- 背景音乐

## 文件结构
birthday-wish/
├── index.html // 主页面
├── js/
│ └── index.js // 核心动画逻辑
├── css/
│ ├── style.css // 主样式
│ ├── password.css // 密码页面样式
│ └── normalize.css // 样式重置
└── audio/
└── birthday.mp3 // 背景音乐

## 修改指南

### 核心修改位置

1. **密码修改** - `index.html` (第45行)

  ```javascript
  const password = "20040919"; // 修改密码
  ```

2. **祝福对象** - `index.html` (第25行)

 ```html
 <h2>亲爱的小张同学</h2>
 ```

4. **祝福语修改** - `js/index.js` (第20行)

  ```javascript
  const birthdayMessages = [
  '小张同学|生日快乐', // 文字|文字：两段文字依次显示
  '#circle 25|🌸', // 圆形特效，25为大小
  '二十岁的你|正青春',
  '#rectangle 20x15|✨', // 矩形特效，20x15为宽高
  '愿你眉眼如初|岁月静好',
  '#circle 20|🎂', // 所有特效都可以搭配emoji
  '愿你前程似锦|梦想成真',
  '#rectangle 25x20|🌟',
  '愿你遇见的|都是美好',
  '#circle 25|💫',
  '愿你一生|欢喜无忧',
  '#circle 30|💝' // 最后的祝福一般用大一点的特效
  ];
  ```

4. **动画时间** - `js/index.js` (第40行)

 ```javascript
 const delay = messages[index].includes('#') ? 6000 : 8000;
 // 特效显示6秒，文字显示8秒
 ```

5. **背景音乐** - `index.html` (第90行)		

 ```html
   <audio id="bgMusic" loop>
   <source src="path/to/birthday-music.mp3" type="audio/mpeg">
   </audio>
 ```

6. **粒子颜色** - `js/index.js` (第250行)

```javascript
   const colors = [
   [255, 182, 193], // 浅粉红
   [255, 192, 203], // 粉红
   [255, 228, 225], // 薄雾玫瑰
   [255, 218, 185], // 桃色
   [255, 240, 245] // 淡紫红
   ];
```

   

7. **背景渐变色** - `css/style.css` (第35行)

```css
.body--ready {
background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
}
```

### 特效命令说明

1. **圆形特效**
- 格式：`#circle 大小|emoji`
- 大小范围：20-30
- 示例：`#circle 🌸`

2. **矩形特效**
- 格式：`#rectangle 宽x高|emoji`
- 推荐尺寸：20x15 到 30x20
- 示例：`#rectangle 20x15|✨`

3. **文字显示**
- 格式：`第一行|第二行`
- 示例：`愿你眉眼如初|岁月静好`

### 注意事项

1. 文字长度：每行建议不超过8个汉字
2. 特效大小：不要超过30，否则可能显示不完整
3. 动画时间：可以根据文字长度适当调整显示时间
4. 音乐文件：确保路径正确，支持mp3格式

## 许可证

MIT License