# TIP

- 菜单图标直接从主题调用
- 遇到循环应用相关的错误时，请将头文件的相关引用放在.cpp文件中之后再次尝试
- 菜单中的窗口和程序主界面无相关继承关系，页面之间通过信号传递信息
- 应用中的读取gsetting值改变获取主题状态对应改变主题的代码需要注释掉，接受菜单模块对应的信号。并且需要用到的gsetting项xxxx，固化当前主题配置选择
- 国际化已适配，翻译文件需要更新一下
- 模块中带有debug开关`DEBUG_MENUMODULE` 宏，需要debug本模块时，将宏值改为1即可。软件上线时debug开关需要关闭掉

## 依赖文件

- 帮助功能需要拉起帮助菜单，该功能依赖`daemonipcdbus.h&cpp`文件库,本文件需要放在该库同级目录下，或修改头文件中的引用路径。
- 窗口已适配窗管，依赖文件`xatom-helper.h&cpp`实现，本文件需要放在该库同级目录下，或修改头文件中的引用路径。

## 信号

- menuModuleClose，点击退出触发此信号
- menuSetThemeStyle(QString str)

## 填充字段

- appName：用来拉起对应帮助菜单
- appVersion：软件版本
- appDesc：软件介绍
- iconName：从主题调用的字段
- conPath：程序的gsetting文件名，从中读取主题状态字段

## 其他

- 需要在gsetting中固化程序当前的主题选择，字段为thememode，有lightonly、darkonly、auto三个值

## 注意

- 有的appicon存在外边框，所以有可能导致布局出现异常。可以在布局中自行调教





