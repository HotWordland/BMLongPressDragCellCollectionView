## 效果演示

<p align="center">
    <img  width="44%" src="Images/1.gif"/>
    <img  width="44%" src="Images/2.gif"/>
    <img  width="44%" src="Images/3.gif"/>
    <img  width="44%" src="https://github.com/liangdahong/ToutiaoDemo/raw/master/Images/001.gif"/>
<p/>

<p align="center">
<a href="https://en.wikipedia.org/wiki/IOS"><img src="https://img.shields.io/badge/platform-iOS-red.svg"></a>
<a href="https://en.wikipedia.org/wiki/IOS_8"><img src="https://img.shields.io/badge/support-iOS%208%2B%20-blue.svg?style=flat"></a>
<a href="https://github.com/liangdahong/BMLongPressDragCellCollectionView/releases"><img src="https://img.shields.io/cocoapods/v/BMLongPressDragCellCollectionView.svg"></a>
<a href="https://en.wikipedia.org/wiki/Objective-C"><img src="https://img.shields.io/badge/language-Objective--C-orange.svg"></a>
<a href="https://github.com/liangdahong/BMLongPressDragCellCollectionView/blob/master/LICENSE"><img src="https://img.shields.io/badge/licenses-MIT-red.svg"></a>
</p>

## 介绍
- 本框架是一个让你轻松实现类似支付宝的拖拽重排功能，支持自定义，`iOS8+`，具体可查看代码。

##  CocoaPods 安装

```ruby
pod 'BMLongPressDragCellCollectionView'
pod install
#import "BMLongPressDragCellCollectionView.h"
```

##  手动安装

- 下载项目 【 `clone https://github.com/liangdahong/BMLongPressDragCellCollectionView.git` 】
-  将 `BMLongPressDragCellCollectionView/Sources/BMLongPressDragCellCollectionView`  文件夹下的全部内容拖拽到你的项目。

## 使用说明

1. `BMLongPressDragCellCollectionView` 是继自 `UICollectionView` ，其使用方式和 `UICollectionView` 一致，只需要把 `UICollectionView` 修改为 `BMLongPressDragCellCollectionView` 即可【支持 Xib，StoryBoard】。
2. 原来的 `UICollectionViewDataSource` 换为 B`MLongPressDragCellCollectionViewDataSource` 
3. 原来的 `UICollectionViewDelegateFlowLayout` 换为 `BMLongPressDragCellCollectionViewDelegate`。
4. 实现数据源方法，内部会使用此方法获取数据源，必须实现。 

```
- (nullable NSArray *)dataSourceWithDragCellCollectionView:(BMLongPressDragCellCollectionView *)dragCellCollectionView;
```
如下：

```
- (NSArray *)dataSourceWithDragCellCollectionView:(BMLongPressDragCellCollectionView *)dragCellCollectionView {
    return self.dataSourceArray;
}
```

5. 实现代理方法，当 Cell 有交换时调用，需要外面保存最新的数据源【如果有交换时，数据源已经更新】，必须实现。

```
- (void)dragCellCollectionView:(BMLongPressDragCellCollectionView *)dragCellCollectionView newDataArrayAfterMove:(nullable NSArray *)newDataArray;
```
如下：

```
- (void)dragCellCollectionView:(BMLongPressDragCellCollectionView *)dragCellCollectionView newDataArrayAfterMove:(nullable NSArray *)newDataArray {
    self.dataSourceArray = [newDataArray mutableCopy];
}
```

## 图文演示
### 在 `Xib`或者 `StoryBoard` 中使用
<img  width="50%" src="Images/xib01.png"/>
<img  width="50%" src="Images/xib02.png"/>
<img  width="50%" src="Images/xib03.png"/>
<img  width="50%" src="Images/xib04.png"/>

- 在 `Xib`或者 `StoryBoard` 中只需要上面的 `3 步`就可以让你的 `UICollectionView` 完美支持拖拽重排了。

### 使用纯代码实现
<img  width="50%" src="Images/code01.png"/>
<img  width="50%" src="Images/code02.png"/>
<img  width="50%" src="Images/code03.png"/>
<img  width="50%" src="Images/code04.png"/>

- 在纯代码实现中只需要上面的 `3 步` 就可以让你的 `UICollectionView` 完美支持拖拽重排了。

## 更多自定义方案

如果要做一些自定义的操作可以通过设置 `BMLongPressDragCellCollectionView` 的相关属性或者实现一些特定的协议方法来处理，可查看 `BMLongPressDragCellCollectionView` 的头文件和 `BMLongPressDragCellCollectionViewDelegate` 与 `BMLongPressDragCellCollectionViewDataSource` 协议。

## 联系
- 欢迎 [issues](https://github.com/liangdahong/BMLongPressDragCellCollectionView/issues) 和 [PR](https://github.com/liangdahong/BMLongPressDragCellCollectionView/pulls)
- 也可以添加如下的微信交流和学习
- <img width="20%" src="Images/wx.jpg"/> 

## 感谢
- 核心实现参考自[XWDragCellCollectionView](https://github.com/wazrx/XWDragCellCollectionView)，特别感谢。

## 相关推荐
- 🖖高性能的自动计算采用 Autolayout 布局的 UITableViewCell 和 UITableViewHeaderFooterView 的高度，内部自动管理高度缓存。
[https://github.com/liangdahong/UITableViewDynamicLayoutCacheHeight](https://github.com/liangdahong/UITableViewDynamicLayoutCacheHeight)

## 其他
- https://github.com/liangdahong/ToutiaoDemo 基于本框架实现的头条频道编辑效果。

## License    
BMLongPressDragCellCollectionView is released under the [MIT license](LICENSE). See LICENSE for details.
