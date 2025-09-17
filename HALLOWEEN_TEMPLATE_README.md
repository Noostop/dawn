# 万圣节购买页模板

## 概述
这是一个专为万圣节活动设计的Shopify产品购买页模板，具有完整的万圣节主题视觉效果和交互动画。

## 文件结构

### 模板文件
- `templates/product.halloween.json` - 万圣节产品页面模板配置
- `sections/main-product-halloween.liquid` - 主要的万圣节产品页面section
- `sections/halloween-product-recommendations.liquid` - 万圣节产品推荐section

### 样式文件
- `assets/section-main-product-halloween.css` - 主要产品页面样式
- `assets/section-halloween-product-recommendations.css` - 产品推荐样式

## 功能特性

### 🎃 万圣节主题元素
- **配色方案**: 橙色(#FF6B35)、紫色(#2D1B69)、金色(#FFD700)
- **装饰元素**: 蜘蛛🕷️、蝙蝠🦇、南瓜🎃、幽灵👻
- **背景动画**: 浮动的万圣节元素
- **特效**: 发光、脉冲、旋转等动画效果

### 📱 响应式设计
- **桌面端**: 完整的双栏布局
- **平板端**: 自适应网格布局
- **移动端**: 单栏垂直布局
- **断点**: 768px, 480px

### 🛒 购买功能
- **万圣节横幅**: 带倒计时的活动横幅
- **产品展示**: 带万圣节边框的产品图片
- **价格显示**: 突出的万圣节风格价格
- **折扣信息**: 动画折扣标签
- **购买按钮**: 万圣节主题的CTA按钮
- **产品推荐**: 万圣节风格的相关产品

### ⚡ 交互动画
- **倒计时器**: 实时万圣节倒计时
- **浮动动画**: 装饰元素的浮动效果
- **悬停效果**: 按钮和卡片的交互反馈
- **加载动画**: 产品卡片的滑入效果

## 使用方法

### 1. 应用模板
在Shopify后台，为特定产品选择 `product.halloween` 模板。

### 2. 自定义设置
模板提供以下可自定义选项：
- 万圣节横幅文本
- 倒计时显示开关
- 折扣百分比
- 特色功能文本
- 颜色主题

### 3. 内容配置
- **横幅标题**: 默认"🎃 万圣节特惠 🎃"
- **横幅副标题**: 默认"恐怖优惠，限时抢购！"
- **购买按钮**: 默认"立即抢购 👻"
- **特色功能**: 快速发货、品质保证、专业客服

## 技术实现

### CSS变量
```css
:root {
  --halloween-orange: #FF6B35;
  --halloween-purple: #2D1B69;
  --halloween-gold: #FFD700;
  --halloween-shadow: rgba(255, 107, 53, 0.3);
  --halloween-glow: rgba(255, 107, 53, 0.6);
}
```

### 关键动画
- `float`: 浮动效果
- `pulse`: 脉冲效果
- `bounce`: 弹跳效果
- `spin`: 旋转效果
- `shimmer`: 闪光效果

### JavaScript功能
- 万圣节倒计时器
- 产品推荐加载
- 动画初始化
- 滚动触发动画

## 浏览器兼容性
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 无障碍功能
- 语义化HTML结构
- ARIA标签支持
- 键盘导航友好
- 屏幕阅读器兼容
- 高对比度模式支持
- 减少动画选项

## 性能优化
- CSS变量减少重复
- 图片懒加载
- 动画硬件加速
- 媒体查询优化
- 背景滤镜优化

## 自定义指南

### 修改颜色主题
在CSS文件中修改`:root`变量：
```css
:root {
  --halloween-orange: #your-color;
  --halloween-purple: #your-color;
}
```

### 添加新动画
```css
@keyframes your-animation {
  0% { /* 起始状态 */ }
  100% { /* 结束状态 */ }
}
```

### 修改断点
```css
@media screen and (max-width: your-breakpoint) {
  /* 响应式样式 */
}
```

## 注意事项
1. 确保所有CSS和JavaScript文件正确加载
2. 测试不同设备和浏览器的兼容性
3. 验证倒计时功能的时区设置
4. 检查产品推荐API的正常工作
5. 确保无障碍功能正常运行

## 更新日志
- v1.0.0: 初始版本，包含完整的万圣节主题功能

## 支持
如需技术支持或功能定制，请联系开发团队。