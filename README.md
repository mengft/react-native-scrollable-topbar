# react-native-scrollable-topbar
基于React Native封装的资讯频道TopBar，常见于新闻客户端，具体实现功能如下：
* TopBar区域可手动滑动(Underline 联动)
* 点击频道实现内容区切换
* 根据内容区(this.props.children)触摸手势实现频道切换
* 频道位置校准，左右边界临界位置处理，实现自动滑动校准

## Installation

```bash
npm install react-native-scrollable-topbar --save
```
```bash
yarn add react-native-scrollable-topbar --save
```

## Import into your project
```js
import ScrollTopBar from "react-native-scrollable-topbar";
```

## Examle useage

```js
<ScrollTopBar
  topBarUnderlineStyle={{}}				                                                    // 下划线样式
  labelList={['推荐', '军事', '政治', '财经', '娱乐', '社会', '生活', '美食', '旅行']}			// 标题栏素材
  topBarInactiveTextColor={Colors.C5}		                                              // label 文字非选中颜色
  topBarActiveTextColor={Colors.CB}		                                                // label 文字选中颜色
  topBarBackgroundColor={Colors.C8}		                                                // 背景颜色
>
  {['推荐', '军事', '政治', '财经', '娱乐', '社会', '生活', '美食', '旅行'].map((e, i) => 
      <ArticleList key={i} index={i} navigation={this.props.navigation} /> 
  )}
</ScrollTopBar>

```

## Properties
属性  | 描述    | 类型  | 默认    
------ | ------ | ------  | ------
topBarUnderlineStyle  | 下划线样式 | ```PropTypes.oneOfType([ ViewPropTypes.style, PropTypes.number ]) ``` | ``` { backgroundColor: '#298eff', height: 4, width: 60, marginTop: -4 } ```
labelList | 频道列表  | ``` PropTypes.array ``` | ['推荐', '军事', '政治', '财经', '娱乐', '社会', '生活', '美食', '旅行']  
topBarInactiveTextColor | 非活跃频道文字颜色  | ``` PropTypes.string ```  | '#aab9ca' 
topBarActiveTextColor | 活跃频道文字颜色  | ``` PropTypes.string ```  | '#298eff' 
topBarBackgroundColor | 背景颜色  | ``` PropTypes.string ```  | '#54657e'
