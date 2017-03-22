#	Chuxin Android Coding Style & 以前在公司的代码规范，可在组内推行

>**初心网络安卓组代码规范说明  @author [JackWong黄绿蓝](http://loranwong.com) ,      [LexLuther梁世宇](http://weibo.com/n/明日叙)**
>最后编辑于 2016年09月21日19:04:25

Table of Contents
=================

   * [1 Project structure 工程结构](#1-project-structure-工程结构)
            * [1.1 Notice 说明](#11-notice-说明)
            * [1.2 Resources directory structure 资源文件夹结构](#12-resources-directory-structure资源文件夹结构)
   * [2 Package Manner 包管理规范](#2-package-manner-包管理规范)
            * [2.1 General 通用](#21-general-通用)
            * [2.2 App 包结构](#22-app-包结构)
   * [3 File Naming 文件命名](#3-file-naming-文件命名)
            * [3.1 Class files 类文件命名](#31-class-files-类文件命名)
            * [3.2 Resources files 资源文件](#32-resources-files-资源文件)
            * [3.3 Drawable files](#33-drawable-files)
            * [3.4 Layout files 布局文件](#34-layout-files-布局文件)
   * [4 Inside Code Naming  代码内部命名](#4-inside-code-naming--代码内部命名)
            * [4.1 Class Variable Naming 类变量命名](#41-class-variable-naming-类变量命名)
            * [4.2 Class Method Naming 类方法命名](#42-class-method-naming-类方法命名)
            * [4.3 layout.xml 布局文件变量命名](#43-layoutxml-布局文件变量命名)
            * [4.4 strings.xml  dimens.xml  colors.xml  xml变量命名](#44-stringsxml--dimensxml--colorsxml--xml变量命名)
            * [4.5 额外注意](#45-额外注意)
    * [5  Code Manner 代码规范](#5--code-manner-代码规范)
    * [6 Constant 内部类解析](#6-constant-内部类解析)
    * [7 Git 提交规范](#7-git-提交规范)

## 1 Project structure 工程结构

#### 1.1 Notice 说明 

New projects should follow the Android Gradle project structure that is defined on the [Android Gradle plugin user guide](http://tools.android.com/tech-docs/new-build-system/user-guide#TOC-Project-Structure). The [BoilerPlate](https://github.com/ribot/android-boilerplate) project is a good reference.

新建工程需要按照最新的Android Gradle的工程结构,在以下定义：[Android Gradle plugin user guide](http://tools.android.com/tech-docs/new-build-system/user-guide#TOC-Project-Structure). 该工程： [BoilerPlate](https://github.com/ribot/android-boilerplate)  是一个很好的参考材料

#####	1.2 Resources directory structure	资源文件夹结构 

*	res
	*	anim
	*	drawable (xml or selector)
	*	mipmap	(pixel image)
	*	layout
	*	values


## 2 Package Manner 包管理规范


#### 2.1 General 通用

* package name ： com.chuxin.[project name]

#### 2.2 App 包结构

```java
* app
	* (class) Constant [后续有文件说明]
	* (class) Application
* ui
	* fragment
	* activity
	* base
	* dialog
	* adapter
	* custom
* service
	* (which servie) ...
* entity 
	* local
	* remote
* manager
	* (which manager) ...
* util
	* (which util)...
```
##	3 File Naming 文件命名

####	3.1 Class files 类文件命名

Class names are written in [UpperCamelCase](http://en.wikipedia.org/wiki/CamelCase). 


For classes that extend an Android component, the name of the class should end with the name of the component; for example: `SignInActivity`, `SignInFragment`, `ImageUploaderService`, `ChangePasswordDialog`.

For utilties class , the name of the class should start with its usage , and ends with `Utils`; for example: `HttpUtils` , `ImageUtils`

>类命名方式采用 `大驼峰` 命名法

>对于继承自安卓组件的类来说，类名应该以该组件名结尾，例如 ： `SignInActivity`, `SignInFragment`, `ImageUploaderService`, `ChangePasswordDialog`.

>对于工具类来说，命名方式应该以其完成功能开始,以 `Utils` 结束 ，例如 ：`HttpUtils` , `ImageUtils`.


#### 3.2 Resources files 资源文件

Resources file names are written in __lowercase_underscore__. 
>资源文件以__小写加下划线__的方式命名

#### 3.3 Drawable files 
 
- Naming conventions for drawables:
 >drawable 文件的命名规范
 
 | Asset Type   | Prefix 前缀           |		Example               |
 |--------------| ------------------|-----------------------------|
 | Action bar   | `ab_`             | `ab_stacked.9.png`          |
 | Button       | `btn_`	            | `btn_send_pressed.9.png`    |
 | Dialog       | `dialog_`         | `dialog_top.9.png`          | 
 | Divider      | `divider_`        | `divider_horizontal.9.png`  |
 | Icon         | `ic_`	            | `ic_star.png`               |
 | Menu         | `menu_	`           | `menu_submenu_bg.9.png`     |
 | Notification | `notification_`   	| `notification_bg.9.png`     |
 | Tabs         | `tab_`            | `tab_pressed.9.png`         |


- Naming conventions for icons:
 >icons文件的命名规范

| Asset Type                      | Prefix 前缀            | Example                      |
| --------------------------------| ----------------   | ---------------------------- | 
| Icons                           | `ic_`              | `ic_star.png`                |
| Launcher icons                  | `ic_launcher`      | `ic_launcher_calendar.png`   |
| Menu icons and Action Bar icons | `ic_menu`          | `ic_menu_archive.png`        |
| Status bar icons                | `ic_stat_notify`   | `ic_stat_notify_msg.png`     |
| Tab icons                       | `ic_tab`           | `ic_tab_recent.png`          |
| Dialog icons                    | `ic_dialog`        | `ic_dialog_info.png`         |


- Naming conventions for selector states:
 >选择器状态文件的命名规范

| State	       | Suffix  尾缀        | Example                     |
|--------------|-----------------|-----------------------------|
| Normal       | `_normal`       | `btn_order_normal.9.png`    |
| Pressed      | `_pressed`      | `btn_order_pressed.9.png`   |
| Focused      | `_focused`      | `btn_order_focused.9.png`   |
| Disabled     | `_disabled`     | `btn_order_disabled.9.png`  |
| Selected     | `_selected`     | `btn_order_selected.9.png`  |


#### 3.4 Layout files 布局文件

Layout files should match the name of the Android components that they are intended for but moving the top level component name to the beginning. For example, if we are creating a layout for the `SignInActivity`, the name of the layout file should be `activity_sign_in.xml`.

>布局文件的命名需要与他所嵌入的安卓组件匹配，但是将组件名称前移到开始处,例如,我们要创建一个名字为 `SignInActivity `, 其名字应该为  `activity_sign_in.xml`.

| Component 组件  | Class Name             | Layout Name                   |
| ---------------- | ---------------------- | ----------------------------- |
| Activity         | `UserProfileActivity`  | `activity_user_profile.xml`   |
| Fragment         | `SignUpFragment`       | `fragment_sign_up.xml`        |
| Dialog           | `ChangePasswordDialog` | `dialog_change_password.xml`  |
| AdapterView Item | ---                    | `item_person.xml`             |


## 4 Inside Code Naming  代码内部命名

```
Important ： 请不要使用拼音以及数字！！！

====== 常用缩写 ======

完整单词 缩写

A
average ——> avg

B
back ——> bk
background ——> bg
break ——> brk
buffer ——> buf

C
color ——> cr(clr)
control ——> ctrl

D
data ——> dat
delete ——> del
document ——> doc

E
edit ——> edt
error ——> err
escape ——> esc

F
flag ——> flg
form ——> frm

G
grid ——> grd

I
increment ——> inc
information ——> info
initial ——> init
insert ——> ins
image ——> img

L
label ——> lab
length ——> len
list ——> lst
library ——> lib

M
manager ——> mngr(mgr)
message ——> msg

O
Oracle ——> Ora

P
panorama ——> pano
password ——> pwd
picture ——> pic
point ——> pt
position ——> pos
print ——> prn
program ——> prg

S
server ——> srv
source ——> src
statistic ——> stat
string ——> str
Sybase ——> Syb

T
temp ——> tmp
text ——> txt

U
user ——> usr

W
window ——> wnd(win)
```


####   4.1 Class Variable Naming 类变量命名

*   公有变量按 `小驼峰` 法命名
*   私有 & 非静态成员变量以 `m` 开头
*   私有 & 静态成员变量以 `s` 开头
*   常量以大写字母和下划线 `_` 组成
*   尽量使用 `功能/描述 + 类型` 的模式 ,如 `mNameTextView`
*   类中变量的组件类型请不要使用缩写
*   注意不要使用 `aa` `bb` `cc3` 这种变态的命名方式 ！！
*   类变量过多时请 `分块摆放` 并且 `写好注释`
*   `接口类` 请直接定义在类的最后


Example:

```java
public class MyClass {
    //静态常量
    public static final int SOME_CONSTANT = 42;
    //公有变量
    public int publicField;
    //私有静态变量
    private static MyClass sSingleton;
    //默认变量
    int mPackagePrivate;
    //私有变量
    private int mPrivate;
    //继承型变量
    protected int mProtected;
}
```

####    4.2 Class Method Naming 类方法命名

*   类方法采用 `小驼峰` 命名法
*   根据函数所完成功能命名 ， 如 `changView()`
*   在函数头写对于函数功能、参数和返回值的注释，如：
 ```java
    /**
     * 获取两个数中最大的一个
     *
     * @param value1 参与比较的第一个数
     * @param value2 参与比较的第二个数
     * @return 两个参数中最大的一个数
     */
    public int max(int value1, int value2) {
        return (value1 > value2) ? value1 : value2;
    }
 ```
 
*   一个函数请尽量保持在 `50行` 之内 ！！


####    4.3 layout.xml 布局文件变量命名

*   `id` 以 `所在组件_类型_命名` 的模式，例如： `@+id/main_tv_name` 、 `@id/chat_btn_send`
*   布局多处重用的请使用 `<include>` 标签
*   所有文本请定义在 `strings.xml` 中 , 如 `@string/app_name`
*   重用dp请定义在 `dimens.xml` 中 , 如  `@dimen/entry_item_height`
*   对应组件缩写表：

| Component 组件  | Abbreviation 缩写       | 
| ---------------- | ---------------------- | 
| Fragment         | `fgm`|
| TextView         | `tv` | 
| ImageView        | `iv` | 
| Button           | `btn`| 
| EditText         | `et` | 
| LinearLayout     | `ll` | 
| ReleativeLayout  | `rl` | 
| normally : FirstSecond | `fs`| 



####    4.4 strings.xml  dimens.xml  colors.xml  xml变量命名

>*   遵循 `完整性` `规范性` `有序性`原则
*   __分块并注释__, 将 使用在不同的 `Activity` 或者 `Fragment` 中的 `xml` 变量 进行分块
*   命名举例 ： 
   `login_error_tips`  __in__  `strings.xml`  
   `login_error_tips_height` __in__ `dimens.xml`
   `login_error_tips_bg` __in__ `colors.xml`


| Prefix 前缀        | Description 描述                      |
| -----------------  | --------------------------------------|
| `error_`             | An error message                      |
| `msg_`               | A regular information message         |       
| `title_`             | A title, i.e. a dialog title          | 
| `action_`            | An action such as "Save" or "Create"  |


####    4.5 额外注意

| Good           | Bad            |
| -------------- | -------------- |
| `XmlHttpRequest` <i class="icon-thumbs-up"></i>| `XMLHTTPRequest`<i class="icon-thumbs-down"></i> | 
| `getCustomerId`  <i class="icon-thumbs-up"></i>| `getCustomerID`<i class="icon-thumbs-down"></i>  | 
| `String url` <i class="icon-thumbs-up"></i>    | `String URL`<i class="icon-thumbs-down"></i>     |
| `long id` <i class="icon-thumbs-up"></i>       | `long ID`<i class="icon-thumbs-down"></i>        |




##  5  Code Manner 代码规范

---
This is __good__

```java
if (condition){
    body();
}
```
This is __bad__:

```java
if (condition) body();  // bad!
```
---
This is __good__:

```xml
<TextView
	android:id="@+id/text_view_profile"
	android:layout_width="wrap_content"
	android:layout_height="wrap_content" />
```
        
This is __bad__ :

```xml
<!-- Don't do this! -->
<TextView
    android:id="@+id/text_view_profile"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" >
</TextView>
```


## 6 Constant 内部类解析

>*   `Constant` 
    *   `CODE`    --> `request_code`，`app_key` 等
    *   `CONFIG`  --> 项目的配置变量, 偏向于调试开发使用，如：`IS_DEBUG`, `SHOW_LOG`
    *   `URL`  --> 网络地址相关
    *   `COUNT`   --> 某些约定的数字，如一次刷新显示的条目数量。__一定要有注释__
    *   `PATH`    --> 路径信息，SD卡路径等
    *   `KEY`    --> 键值对的键的信息,如 `Bundle` 中的键
    

## 7 Git 提交规范

**基本要求**

- 分段

例子：

```
(Git test) Modify CircleImageView to show rounded rectangle

https://trello.com/c/M7u5h0QA

The original function can be used normally,
To show rounded rectangle, you need add param "bao:round" to XML file,
it's value is the rounded rectangle's corner radius.
```

**第一行**
:   作为标题，这在 Git 中就会做为默认显示的部分，如图中深黑色字：
    ![提交信息的显示](http://t1.qpic.cn/mblogpic/2da122c89f961ea51a7a/2000.jpg)

**第二行**
:   留空！因为通常在设置了邮件提醒的 Git 系统中，第二行的空行是作为分隔标题和正文的存在。

**第三行**
:   开始就是详细说明了。可以加上对此次修改的问题的链接，或者描述。如果有用到 `issue` 的话可以写上 `issue #[issue id]`，或者附上 __trello__ 的链接。

~~建议全部用英文写，其他字符有乱码的可能。~~ 并不会乱码

- 粒度

>说的是做的修改的粒度。如果你一天做了很多的修改，但是就只提交了一次，那么你的粒度就有点大了。
>
>这样在你描述你的行为的时候就会显得模糊，如果你详细描述的话，提交信息会变得长篇大论。
>
>但也不要做一点提交一点，这样粒度就会变得太小，会导致一天到晚在写提交信息，没有必要。
>
>在我看来，这个事情真的只能凭感觉提交，用经验来做判断。因为一个BUG可能可大可小，大的话，你就得分割修复。
>
>如果小，那么就一次提交修复就可。
>
>粒度的掌握绝对会影响你的提交信息，因为二者是一一对应的。


- 宽度

>是的，是宽度，不是长度。
>
>和代码一样，如果你平时注意的话，就不要让你的代码在一行上超过80，不然谁读代码都不好受，包括你自己。
>
>所以提交信息的宽度也有限制。
>
>分别是标题不要超过50，内容部分不要超过70。




----------

**大概大家都会的没什么用的小Tips：**

- 使用 `git commit` 命令并进入 `Vim` 编辑提交信息，写完后按 `Esc` 确保不在编辑状态，然后输入 `:wq` 回车退出并提交。
- 直接使用 `Android Studio` 自带的 VCS 也很方便。

----------

**参考资料：**

- [Git - 如何写好你的提交信息？](http://segmentfault.com/a/1190000002583308)
- [写出好的 commit message](https://ruby-china.org/topics/15737)
