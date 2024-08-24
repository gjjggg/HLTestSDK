# SLFoundation

## 介绍

`SLFoundation`是一个iOS工程中各种基类的库。使用后，可快速进行新建工程和加快业务开发。

`SLFoundation`包含以下几个部分

#### ViewController

`SLViewController`是所有`ViewController`的基类，支持方便的设置`UIStatusBarStyle`,设置导航栏隐藏。

`SLListBaseViewController`是方便列表类快速添加下拉刷新和下来加载更多。

`SLTableBaseViewController`和`SLCollectionBaseViewController`是方便带有列表视图的`SLViewController`

#### Request

`SLHttpRequest`提供新建网络请求的基类

`SLBaseRequest`在`SLHttpRequest`上增加类方法的支持，可以快速的新建请求,未来考虑合并两个请求。

`SLNetworkMonitorManager`是网络状态监控类，可获取网络状态等

`YTKNetworkAgent+SLAdd.h`配合`SLHttpRequest`可进行全局网络请求状态的监控，可进行一下全局操作。

#### Model

`SLBaseModel`是Model的基类，支持归档解档，hash方法，支持descrition方法，在调试状态下可输出所有属性的值。

## 示例程序

想要运行示例程序, 把工程克隆下来, 然后运行 `pod install` 即可运行。

## 需要

iOS 9及以上

## 安装

`SLFoundation` 通过 `CocoaPods`私有仓库安装。

私有仓库名字为[SLSpecs](https://git.shunliandongli.com/shunlian_ios/SLSpecs.git)

因此，首先在podfile头文件中添加如下：

```ruby
source 'https://github.com/CocoaPods/Specs.git'
source 'https://git.shunliandongli.com/shunlian_ios/SLSpecs.git'
```

然后在`podfile`的`target`中添加

```ruby
pod 'SLFoundation'
```

最后运行 `pod install` 即可。

## 更新日志

###### 1.0.0

- SLBaseModel遵循NSSecureCoding协议

###### 0.0.26

- SLViewController添加隐藏导航栏时自定义导航栏返回按钮显示

###### 0.0.25

- iOS15更新之后 导航条透明问题

###### 0.0.24

- SLCollectionViewController添加一次性添加CollectionView的方法

###### 0.0.23

- 修复SLCollectionViewController view时机调用错误的问题

###### 0.0.22

- 拆分SLNetwork

###### 0.0.20 0.0.21

- SLNavigationController添加两个辅助字段
- SLBaseRequest增加预设关联视图。关联视图用于显示loadingview，toast等

###### 0.0.19

- 为了升级QMUIKit，升级最低适配版本号iOS10

###### 0.0.18

- SLMaskView冲突判断方法改为类方法

###### 0.0.17

- 弹窗引入到本库，增加弹窗冲突的判断

###### 0.0.13 0.0.14 0.0.15

- 请求是否成功的判断可由YTKNetworkAgent的delegate去返回

###### 0.0.12

- 优化SLBaseRequest，SLListBaseView添加标记是否加载过参数的标识

###### 0.0.11

- 对于网络请求类初始化的优化

###### 0.0.9 & 0.0.10
- 对于简单类型(就一种cell)tableView。添加快速创建tableView。使用方法看Demo
- SLTableBaseViewController 创建时 推荐使用 -(instancetype)initWithTableViewStyle:(UITableViewStyle)style;

###### 0.0.8

- YTKNetwork添加Post上传进度的支持

###### 0.0.5

- 解决网络请求失败的问题

###### 0.0.4

- 解决图片加载不出来的bug

###### 0.0.3

- 添加头文件的支持
- 添加空白页面占位图资源文件

###### 0.0.2
`SLCollectionBaseViewController`添加`- (instancetype)initWithCollectionViewLayout:(nullable UICollectionViewLayout *)layout`在初始化时添加UICollectionView

`SLTableBaseViewController`添加`- (instancetype)initWithTableViewStyle:(UITableViewStyle)style`在初始化时添加UITableView
添加`SLTableBaseView`和`SLCollectionBaseView`,类比`SLTableBaseViewController`和`SLTableBaseViewController`
即在`UIView`上添加`UITableView`和`UICollectionView`的支持
###### 0.0.1
顺联动力iOS开发基础库
