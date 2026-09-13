问题反馈与建议：[https://github.com/ESLyric/feedback/issues](https://github.com/ESLyric/feedback/issues)

# v1.0.7.0
**新增**
- 布局元素支持`transition`属性：CSS 风格的属性过渡动画，元素折叠/展开时其槽位与兄弟元素平滑重排
```xml
<label caption="%title%" transition="size 300ms cubic-out, background-color 150ms"/>
```
- 布局元素支持`transform`属性：渲染侧变换，支持`:hover`/`:pressed`/`:disabled`状态覆盖，`transition`同步支持`transform`
```xml
<button transform="scale(0.96) :hover scale(1.08) :pressed scale(0.98)" transition="transform 200ms" clip="none"/>
```
- 布局元素支持`box-shadow`属性：CSS 风格的阴影/辉光，支持状态覆盖，颜色支持`{highlight}`、`{dominant-color}`等全部布局颜色格式
```xml
<albumart box-shadow="0 10px 26px rgba(255,94,138,.4)"/>
```
- 布局颜色支持使用封面主题色`{dominant-color}`及`{dominant-color1}`~`{dominant-color4}`
```xml
<label caption="%title%" text-color="{dominant-color}"/>
```
- 布局元素支持圆角与边框`border-radius`/`border-width`/`border-color`，`container`支持渲染背景
```xml
<container background-color="rgba(0,0,0,0.35)" border-radius="6" border-width="1" border-color="{highlight}"/>
```
- 布局元素支持显式指定裁剪模式`clip`，使用`clip="none"`可让`transform`放大时溢出的内容显示
```xml
<albumart transform=":hover scale(1.1)" clip="none"/>
```
- 布局可视化频谱新增`wave2`风格，使用 D2D 几何绘制，抗锯齿效果更好
```xml
<visualization type="spectrum" spectrum="wave2"/>
```
- 布局可视化频谱`classic`风格新增峰值保持线，支持`peak-color`/`peak-height`/`peak-gap`/`peak-fall`/`peak-hold`配置
```xml
<visualization type="spectrum" spectrum="classic" peak="1" peak-color="{highlight}"/>
```
- 歌词新增弹性滚动样式，面板右键菜单"滚动样式"可选择；支持脱手拖拽调整播放进度、跳转后动画滚动至目标、播放行放大字体及颜色过渡
- 歌词解析恢复支持 v3 时间戳
- 歌词编辑器支持 ESC 关闭
- 桌面歌词、浮动歌词设置独立成页面
- 布局新增 tracer 调试工具，便于排查布局渲染问题
- 外部JS面板控制接口新增文本样式及自定义选项开关等接口，详见[外部JS面板控制接口](外部JS面板控制接口)


**修复**
- 修复使用原生提示控件`native tooltip`并开启多线程渲染时可能死锁的问题
- 修复布局`tooltip`字体未正常恢复，导致其它元素字体异常的问题
- 修复停止播放时图片背景过渡的最后一张半透明图片会停留约1秒的问题
- 修复桌面歌词弹出播放列表菜单、在外部点击关闭菜单后面板未恢复透明状态的问题
- 修复歌词面板后备信息对齐等问题
- 修复列表下拉`combobox`所在行闪烁的问题
- 修复外部JS接口`SetLayoutName`在未启用自定义布局时不生效的问题
- 修复外部JS接口行间距/句间距传负值，以及边距参数在多个面板间串值的问题
- 修复外部JS接口`SetTextRenderer`返回失败导致脚本异常的问题


**优化**
- 优化`wave`风格频谱，新增`fade-width`等可调参数
- 布局`locales`支持新的配置形式
- 布局`schema`更新，隐藏私有属性并补充属性文档
- 优化面板高级设置体验，调整自定义菜单设置位置
- 更新本地化


**更改**
- 布局文本轮廓宽度单位统一为像素，旧布局中设置的轮廓宽度需要按新单位调整
- 调整全屏应用检测逻辑
