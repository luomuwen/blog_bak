title: "ViewController的学习"
date: 2015-10-14 22:50:45
description: 记录自己对于官方ViewController的学习
tags:
---
###1. View Controller基础

####1.1 Sceens, Windows以及Views 创建了可视化的接口
####1.2 View Controllers管理Views
* Every view is controlled by only one view controller.
* Each view controller interacts with a subset of your app’s data. 
* Because each view controller provides only a subset of the user experience, the view controllers must communicate with each other to make this experience seamless.

####1.3 View Controller的分类
* Content View Controller
<pre>
	1. 显示数据给用户
	2. 搜集用户数据
	3. 运行指定的任务
	4. 为一系列的操作或者命令导航
</pre>

* Table View Controller
* Container View Controller
* Navigation Controller
* Tab Bar Controller
* Split View Controller
* Popover Controller
	此Popover Controller是目前来看唯一不继承自UIViewController的。
* Page View Controller
####1.4 View Controller内容的显示方式
* 使View Controller成为window的root view controller
* 使View Controller成为容器的子View Controller
* 在Popover Controller中显示View Controller （iPad only）
* 在其他的ViewController中展现

####1.5 通过多个View Controller构建你的应用
* Parent-Child

* Sibling 

* 作为另外一个界面的短暂的显示

* Data Flow

####1.6 Storyborad帮助你设计你的用户界面

###2 在你的App中使用View Controllers

####2.1 通过Stroyboard创建View Controller
* 两个View Controller的关系
	1. segue, 目标View Controller在Segue触发之后实例化
	2. Containment， 子View Controller在父View Controller实例化之后实例化。
	3. 其他，不自动实例化，而是通过编程的方式。 
		
		
* Storyboard上的Segue，View Controller都是通过id进行指定。
	
* 你的项目中可以包含一个或者多个Storyboard，如果存在main storybarod，iOS会自动加载main storyborad。
	
* iOS通过Storyboard加载程序的过程：
	1. 创建一个window
	2. 加载main storyboard创建它的初始View Controller
	3. 将Window的rooteViewController设置为刚刚创建的View Controller，然后使window在屏幕上可见。
		
* Segue
	
	
* 通过编程的方式触发Segue	
```objectivec
	performSegueWithIdentifier:@"" sender:
```
	
* 通过编程的方式获得Storyboard上的View Controller的实例
```objectivec
	UIStoryboard* storyboard = [UIStoryboard storyboardWithName:@"main" bundle:nil];
	TestViewController* viewController = [storyboard instantiateViewControllerWithIdentifier: @"TestViewController"];
```

* 在多个Storyboard跳转需要通过编程的方式
	一般来说，没有任何规定不让你创建多个storyboard，但是一般在这些情况下，你可以创建多个：
	1. 大量的开发团队，每个团队负责不同的用户界面
	2. 使用第三方的一些库，这里库里面已经内置了一堆的storyboard
	3. 你的内容需要在额外的一些屏幕上显示。
	怎么跳转呢？这里并没有讲。




####2.2 实例化一个没有Storyboard的View Controller
 
 一般来说，三思，通过Objective－C的方式（通常而言都是 alloc init）。Storyboard所有的好处你都不能够享受，你得自己搞定一切。


####2.3 通过编程的方式显示一个View Controller的内容
1. 设置成window的rootViewController
2. 设置成一个可视的View Controller的子Controller
3. presentViewController: animated: completion:
4. popover（iPad only）

###创建自定义内容的View Controllers

####3.1 View Controller 内容概览

#####3.1.1 View Controller管理资源

#####3.1.2 View Controller管理View

#####3.1.3 View Controller响应事件

#####3.1.4 View Controller与其他View Controller交互

#####3.1.5 View Controller与容器的协作

#####3.1.6 View Controller被其他View Controller展现

####3.2 设计你自己的View Controller

设计View Controller中，需要关注的一些问题：
* 要不要使用Storyboard来实现？
* 什么时候实例化？
* 它需要显示什么样的数据？
	这里他有几种通用的模式：
		* 从其他的Controller那里接受数据然后显示它，不提供方式编辑它。没有数据返回。
		* 当前Controller允许用户输入新数据，在数据输入完成之后，将数据传给另外的Controller。
		* 当前Controll而接收数据，允许用户编辑它。编辑完成之后，将数据发送到另外的Controller。
		* Controller不接受，也不发送任何数据。它只显示静态View。
		* Controller不接受，也不发送任务数据。它内部实现了一套不暴露给外部的数据加载机制。
	_这里没有限定只能用上面的几种方式_
	
* 它运行的是什么任务？
* 它的视图在屏幕上是如何显示的？
* 它与其他View Controller的关系？

####3.3 View Controller设计的例子

1. 任务描述


####3.4 实现View Controller的备忘录
通过Storyboard创建View Controller，其中的View，button都应该放在category中。

###View Controllers中的资源管理



###对显示相关的响应

###改变View Controller中view的大小

###在响应链(Responder Chain)中使用View Controller

###面对多个接口的支持

###从View Controller的角度看无障碍访问（Accessibility from the View Congtroller's Perspective）

###从其他的View Controller中展现View Controller

###不同View Controllers中的坐标

###在View Controller中实现编辑模式

###创建自定义的Segue

###创建自定义的容器View Controller

