# 摄像机的裁剪和视野

###### *version :2.7.0beta   Update:2020-6-11*

#### 	远近距离的裁剪

​	摄像机还可以设置远近距离的裁剪，只显示远近距离之间的场景模型，之外的模型不进行渲染显示。它最大的优势在于提高游戏的性能。

创建摄像机时，摄像机构造函数会默认剪切为近距0.3米，远距为1000米。开发者可以在构造函数中设置或通过摄像机属性进行设置。

![](img/1.png)<br>（图1）

```typescript
    //创建摄像机时初始化裁剪(横纵比，近距裁剪，远距裁剪)
    var camera = new Laya.Camera( 0, 0.1, 100);
    //近距裁剪
    camera.nearPlane=0;
    //远距裁剪
    camera.farPlane=100;
```

**tips**：一般在游戏中，我们会把雾效与摄像机剪切同时使用，雾效远距以外的地方基本都看不清楚，这时就可以设置远距离剪切，提高游戏渲染性能。

#### 摄像机视野

摄像机视野类似于焦距，通过视野参数的调整，可以看到视图中的场景范围、透视的近大远小变化，它是通过角度值进行调整，角度越大，视野范围越大，开发者可以根据自己的需求进行设置。

```typescript
//设置相机的视野范围90度
camera.fieldOfView = 90;
```
