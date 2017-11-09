.. _doc_scenes_and_nodes:

Scenes and nodes
场景与节点
================

Introduction
简介
------------

.. image:: img/chef.png

Imagine for a second that you are not a game developer anymore. Instead,
you're a chef! Change your hipster outfit for a toque and a double
breasted jacket. Now, instead of making games, you create new and
delicious recipes for your guests.

想象一下，你不再是一个游戏开发者，而是一位大厨，你不再是制作游戏，而是为嘴馋的客户准备一道大餐。

So, how does a chef create a recipe? Recipes are divided into two
sections: the first is the ingredients and the second is the
instructions to prepare it. This way, anyone can follow the recipe and
savor your magnificent creation.

那么，大厨该怎样挑选食谱呢？食谱包含两部分：原材料和准备工作。这样，每个人都可以根据食谱创建出伟大的料理！

Making games in Godot feels pretty much the same way. Using the engine
feels like being in a kitchen. In this kitchen, *nodes* are like a
refrigerator full of fresh ingredients with which to cook.

用Godot制作游戏跟厨师挑选食谱大同小异，它就像一个厨房，而 *节点(node)* 就是冰箱中准备下锅的火鸡。 

There are many types of nodes. Some show images, others play sound,
other nodes display 3D models, etc. There are dozens of them.

节点有很多类型，显示图片、播放声音、显示3D模型等等。

节点(Nodes)
-----

But let's start with the basics. Nodes are fundamental building blocks for
creating a game. As mentioned above, a node can perform a variety of specialized 
functions. However, any given node always has the following attributes:

让我们从最基本的开始。节点是制作游戏的最基本的单位，就像上面提到的，节点提供了很多不同功能的方法，但节点始终拥有以下属性

-  It has a name.
- 名称(name)
-  It has editable properties.
- 可编辑(editable)
-  It can receive a callback to process every frame.
- 在运行时接收回调
-  It can be extended (to have more functions).
- 可继承
-  It can be added to other nodes as children.
- 可以作为作为子节点添加到其他节点

.. image:: img/tree.png

The last one is very important. Nodes can have other nodes as
children. When arranged in this way, the nodes become a **tree**.
最后一点非常重要。节点可以作为子节点添加到其他节点，按照这个规则，所有的节点就形成了一个 **节点树(tree)**

In Godot, the ability to arrange nodes in this way creates a powerful
tool for organizing projects. Since different nodes have different
functions, combining them allows for the creation of more complex functions.

在Godot中，节点的这种能力为制作大型游戏提供了强力的支持。不同的节点有不同的功能，合理的组合便可以实现更复杂的功能。

Don't worry if this doesn't click yet. We will continue to explore this over
the next few sections. The most important fact to remember for now is that
nodes exist and can be arranged this way.

我们将在后面详解节点，现在你只需要记住节点的存在。

Now that the concept of nodes has been defined, the next logical
step is to explain what a scene is.



场景(Scenes)
------

.. image:: img/scene_tree_example.png

Now that the concept of nodes has been defined, the next logical
step is to explain what a Scene is.

现在，节点的概念你应该清楚了，下面介绍场景。

A scene is composed of a group of nodes organized hierarchically (in
tree fashion). Furthermore, a scene:
场景就是一组节点的集合，它有一下特点：


-  always has only one root node.
-  始终只有一个根节点
-  can be saved to disk and loaded back.
-  可以保存在硬盘上和被加载
-  can be *instanced* (more on that later).
-  可以被 *实例化(instanced)*

Running a game means running a scene. A project can contain several scenes,
but for the game to start, one of them must be selected as the main scene.

游戏的运行以为着某个场景的运行。一个项目可以包含若干场景，但在游戏开始时，其中一个必须被设置为主场景。

Basically, the Godot editor is a **scene editor**. It has plenty of tools for
editing 2D and 3D scenes as well as user interfaces, but the editor is based on
the concept of editing a scene and the nodes that compose it.

基本上，Godot编辑器可以被称为 **场景编辑器**，它有很多用来编辑2D或3D场景的工具。

Creating a new project
----------------------

创建一个新项目
---------------------

Let's make these abstract concepts more concrete with an example. Following a
long tradition in tutorials, we'll start with a "Hello World" project.
This will introduce us to using the editor.

让我们来点儿实际的东西。在啰嗦了一大堆后，我们从一个 "Hello World" 项目开始来介绍编辑器。

If you run the godot executable outside of a project, the Project Manager
appears. This helps developers manage their projects.

.. image:: img/project_manager.png

To create a new project, click the "New Project" option. Choose and create a
path for the project and specify the project name "New Project":

点击 "New Project" ,选择路径，创建工程：

.. image:: img/create_new_project.png

Editor
------

Once you've created the "New Project", then open it. This will open the Godot
editor:

然后，你会看到这个：

.. image:: img/empty_editor.png

As mentioned before, making games in Godot feels like being in a
kitchen, so let's open the refrigerator and add some fresh nodes to the
project. We'll begin with a "Hello World!" message that we'll put on the
screen.

前面提到过，做游戏就像炒菜，那就让我们从冰箱里拿点儿node出来吧。

To do this, press the "New Node" button (which looks like a plus symbol):

点击"New Node"按钮：

.. image:: img/newnode_button.png

This will open the Create Node dialog, showing the long list of nodes
that can be created:

一个长长的node列表：

.. image:: img/node_classes.png

From there, select the "Label" node first. Searching for it is probably
the quickest way:

选择 "Label" ，也可以直接搜索：

.. image:: img/node_search_label.png

And finally, create the Label! A lot happens when Create is pressed:
然后：

.. image:: img/editor_with_label.png

First of all, the scene changes to the 2D editor (because Label is a 2D Node
type), and the Label appears, selected, at the top left corner of the viewport.

首先，场景切换到了2D编辑器，Label 节点出现在了视窗的左上角

The node appears in the scene tree editor (box in the top left
corner), and the label properties appear in the Inspector (box on the
right side).

The next step will be to change the "Text" Property of the label. Let's
change it to "Hello, World!":
设置 "Text" 属性：

.. image:: img/hw.png

Ok, everything's ready to run the scene! Press the PLAY SCENE Button on
the top bar (or hit F6):
好了，一切准备就绪，点击 PLAY SCENE 按钮 (或F6):

.. image:: img/playscene.png

Aaaand... Oops.

哦喝~

.. image:: img/neversaved.png

Scenes need to be saved to be run, so save the scene to something like
hello.tscn in Scene -> Save:

必须先保存场景，点击 Scene -> Save ：

.. image:: img/save_scene.png

And here's when something funny happens. The file dialog is a special
file dialog, and only allows you to save inside the project. The project
root is "res://" which means "resource path". This means that files can
only be saved inside the project. For the future, when doing file
operations in Godot, remember that "res://" is the resource path, and no
matter the platform or install location, it is the way to locate where
resource files are from inside the game.

这下有意思了。对话框只允许在项目目录内选择。项目根目录为 "res://" ，这个目录也叫 "resource path"。
这表示你只能在项目内保存文件。
以后，你必须记住，在Godot中进行文件操作，"res://" 就是资源目录，且与平台无关。

After saving the scene and pressing run scene again, the "Hello, World!"
demo should finally execute:

保存场景后并运行：

.. image:: img/helloworld.png

Success!

大功告成！

.. _doc_scenes_and_nodes-configuring_the_project:

Configuring the project
-----------------------

配置项目：
-----------------------

Ok, it's time to configure the project. Right now, the only way to run
something is to execute the current scene. Projects, however, may have several
scenes, so one of them must be set as the main scene. This is the scene that
will be loaded any time the project is run. 

现在来看下如何配置项目。目前为止，要看到效果必须得运行当前场景，然后，一个项目可能会有多个场景，因此必须有一个主场景，它将在游戏运行时被加载。

These settings are all stored in a project.godot file, which is a plaintext
file in win.ini format (for easy editing). There are dozens of settings that
you can change in this file to alter how a project executes. To simplify this
process, Godot provides a project settings dialog, which acts as a sort of
frontend to editing a project.godot file.

项目配置保存在一个 project.godot 的init格式的文件中，针对场景有很多配置项，godot提供了对话框以方便我们进行配置。

To access that dialog, select Project -> Project Settings. Try it now.

选择 Project -> Project Settings

Once the window opens, let's select a main scene. Locate the
`Application/Run/Main Scene` property and click on it to select 'hello.tscn'.

选择一个主场景 `Application/Run/Main Scene`

.. image:: img/main_scene.png

Now, with this change, when you press the regular Play button (or F5), this
scene will run, no matter which scene is actively being edited.

然后，点击 Play 按钮（或者F5），主场景就运行起来了。

The project settings dialog provides a lot of options that can be saved to a
project.godot file and shows their default values. If you change a value, a
tick is marked to the left of its name. This means that the property will be
saved to the project.godot file and remembered.

As a side note, it is also possible to add custom configuration options and 
read them in at run-time using the :ref:`ProjectSettings <class_ProjectSettings>` singleton.

To be continued...
------------------

This tutorial talked about "scenes and nodes", but so far there has been
only *one* scene and *one* node! Don't worry, the next tutorial will
expand on that...
