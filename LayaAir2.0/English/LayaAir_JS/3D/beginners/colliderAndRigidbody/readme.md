#Collider and Rigid Body

The operation of adding collision body and rigid body is involved in the simple introduction. The specific operation will be explained in this chapter.

The 3D Collider in 2.0 is Physics Collider. The rigid body of 3D is Rigidbody 3D.

To produce a collision, a Rigidbody and a collider must be added to the game object. Rigidbody allows the object to move under physical influence. Colliders are a class of physical components that need to be added to the game object with rigid bodies to trigger collisions. If two rigid bodies collide with each other, the physical engine will calculate the collision unless two objects collide with each other. In physical simulation, rigid bodies without colliding bodies will pass through each other.

Necessary conditions for collisions: Both objects must have a Physics Collider, and one must also have a Rigidbody 3D rigid body.

Collision box: Collider Shape is a shape box in which the model performs physical operations and collisions in the 3D world.

###1. Adding Colliders and Rigid Bodies

First, we create a simple ball and add colliders and rigid bodies to the ball.


```javascript

//新建一个球体模型
var sphere = this.scene.addChild(new Laya.MeshSprite3D(new Laya.SphereMesh(1)));
//给球体添加碰撞器
var spherePhy = sphere.addComponent(Laya.PhysicsCollider);
//新建一个球形的碰撞盒
var sphereShape = new Laya.SphereColliderShape(1)

/* 没有刚体时：
//给碰撞器添加碰撞盒
spherePhy.colliderShape = sphereShape;
*/
//有刚体
 //给球添加刚体
 var sphereRigid = sphere.addComponent(Laya.Rigidbody3D);
//将碰撞盒添加到刚体上
shpereRigid.colliderShape = sphereShape;
```

Different models just need to create different Mesh and Collider Shape.**Be careful not to add shapes to rigid bodies and colliders at the same time**Here is the effect of the ball.

![图](img/1.png)

###2. Simple cases

After knowing how to add colliders and rigid bodies, you can boldly create a simple scene to test this part of the function.

To synchronize the collision and display, you need the same model as the collision box.

#####Main class:


```javascript

import GameConfig from "./GameConfig";
import SceneScript from "./script/SceneScript"; 
class Main {
         constructor() {
            //初始化引擎
            Laya3D.init(0, 0);
            //适配模式
            Laya.stage.scaleMode = Laya.Stage.SCALE_FULL;
            Laya.stage.screenMode = Laya.Stage.SCREEN_NONE;
            //开启统计信息
            Laya.Stat.show();
           	Laya.loader.load("res/layabox.png",Laya.Handler.create(this,this.loadComplete));
		}        
		
        loadComplete(){
			var _scene = new Laya.Scene3D();
            Laya.stage.addChild(_scene);
            _scene.addComponent(SceneScript);
        }
    }

//激活启动类
new Main();
```


#####Script class:


```javascript


export default class SceneScript extends Laya.Script3D{
    constructor(){
        super();
    } 

    onAwake(){
        this.scene = this.owner;
    }  

    onStart(){
        var camera =this.scene.addChild(new Laya.Camera( 0, 0.1, 100));

        camera.transform.translate(new Laya.Vector3(0, 5, 20));
        camera.transform.rotate(new Laya.Vector3( 0, 1, 0), true, false);
        camera.clearColor = null;
        
        var directionLight= this.scene.addChild(new Laya.DirectionLight());
        directionLight.diffuseColor = new Laya.Vector3(0.6, 0.6, 0.6);
        directionLight.transform.worldMatrix.setForward(new Laya.Vector3(1, -1, 0));


        //添加球体模型
        var sphere = this.scene.addChild(new Laya.MeshSprite3D(new Laya.SphereMesh(1)));
        sphere.transform.translate(new Laya.Vector3(0,1,0));
        sphere.meshRenderer.material = new Laya.BlinnPhongMaterial();

        //添加正方体模型
        var cube = this.scene.addChild(new Laya.MeshSprite3D(new Laya.BoxMesh(2,2,2)));
        cube.transform.translate(new Laya.Vector3(4,3,0));
        cube.meshRenderer.material = new Laya.BlinnPhongMaterial();

        //圆柱体模型
        var cylinder = this.scene.addChild(new Laya.MeshSprite3D(new Laya.CylinderMesh(1,2)));
        cylinder.transform.translate(new Laya.Vector3(8,5,0));
        cylinder.meshRenderer.material = new Laya.BlinnPhongMaterial();
        
        //胶囊体模型
        var capsule = this.scene.addChild(new Laya.MeshSprite3D(new Laya.CapsuleMesh(0.5,2)));
        capsule.transform.translate(new Laya.Vector3(-4,1,0));
        capsule.meshRenderer.material = new Laya.BlinnPhongMaterial();

        //圆锥模型
        var cone = this.scene.addChild(new Laya.MeshSprite3D(new Laya.ConeMesh(0.5,2)));
        cone.transform.translate(new Laya.Vector3(-8,1,0));
        cone.meshRenderer.material = new Laya.BlinnPhongMaterial();
        //添加物理组件
        sphere.addComponent(Laya.PhysicsCollider);
        cube.addComponent(Laya.PhysicsCollider);
        cylinder.addComponent(Laya.PhysicsCollider);
        capsule.addComponent(Laya.PhysicsCollider);
        cone.addComponent(Laya.PhysicsCollider);

        var sphererigid = sphere.addComponent(Laya.Rigidbody3D);
        var cuberigid = cube.addComponent(Laya.Rigidbody3D);
        var cylinderrigid = cylinder.addComponent(Laya.Rigidbody3D);
        var capsulerigid = capsule.addComponent(Laya.Rigidbody3D);
        var conerigid = cone.addComponent(Laya.Rigidbody3D);

        sphererigid.colliderShape = new Laya.SphereColliderShape(1);
        cuberigid.colliderShape = new Laya.BoxColliderShape(2,2,2);
        cylinderrigid.colliderShape = new Laya.CylinderColliderShape(1,2);
        capsulerigid.colliderShape = new Laya.CapsuleColliderShape(0.5,2);
        conerigid.colliderShape = new Laya.ConeColliderShape(0.5,2);
        //添加一个地板
        var floor = this.scene.addChild(new Laya.MeshSprite3D(new Laya.PlaneMesh(100,10)));
        //给地板添加物理组件
        var floorCollicar = floor.addComponent(Laya.PhysicsCollider);
        // 添加collidershape
        floorCollicar.colliderShape = new Laya.BoxColliderShape(100,0,10);
        //给地板一个角度
        floor.transform.rotate(new Laya.Vector3(0,0,0.5),false);


        //材质相关
        var material = new Laya.BlinnPhongMaterial();
        Laya.Texture2D.load("res/layabox.png", Laya.Handler.create(null, function(tex) {
            material.albedoTexture = tex;
        }));
        sphere.meshRenderer.material = material;
        cube.meshRenderer.material = material;
        cylinder.meshRenderer.material = material;
        capsule.meshRenderer.material = material;
        cone.meshRenderer.material = material;
    }
    }  
```


In this case, only five kinds of geometry are simply used. The concrete effect is shown as follows:

![图](img/1.gif)

###3. Exported objects add rigid bodies or Colliders

**If a rigid body is needed for derivation, the collider is preferred.**

#####(1) If the derived object has rigid body and collider, it can be used directly.

#####(2) If the derived object does not have colliders and rigid bodies, physical components need to be added.

The grid collision box we use here


```javascript

//////读取导出的lh文件
		Laya.Sprite3D.load("Conventional/shoot.lh",Laya.Handler.create(this,function(sp){
				//获取你需要素材
                var cube = sp.getChildAt(0);
                cube.transform.translate(new Laya.Vector3(0,3,0));
                this.scene.addChild(cube);
                var cubeCollider = cube.addComponent(Laya.PhysicsCollider);
				//网格触发器
                var cubeShape = new Laya.MeshColliderShape();
				//通过导出的网格来获取shape
                cubeShape.mesh = cube.meshFilter.sharedMesh;
				//如果不需要刚体
				//cubeCollider.colliderShape = cubeShape;
				//需要刚体
                var cubeRigid = cube.addComponent(Laya.Rigidbody3D);
                cubeRigid = cubeShape;

		}));
```


#####(3) If the derived object has a collider, but there is a need to add a rigid body

There are two methods: one is to use the grid collision box, the other is to get the collision box from the collider and give it to the rigid body. But both methods need to clear the collision box on the collider. In the second method, it should be noted that the same collision box can not be added to the collider and rigid body at the same time.


```javascript

	//方法一
      Laya.Sprite3D.load("Conventional/shoot.lh",Laya.Handler.create(this,function(sp){
                var cube = sp.getChildAt(0);
                cube.transform.translate(new Laya.Vector3(0,3,0));
                this.scene.addChild(cube);
				//移除之前的碰撞盒
                var cubeCollider = cube.getComponent(Laya.PhysicsCollider);
                cubeCollider.colliderShape = null;
				//添加刚体与碰撞盒
                var cubeRigid = cube.addComponent(Laya.Rigidbody3D);
                var cubeShape = new Laya.MeshColliderShape();
                cubeShape.mesh = cube.meshFilter.sharedMesh;
                cubeRigid.colliderShape = cubeShape;
        }));

	///方法二		
	Laya.Sprite3D.load("Conventional/shoot.lh",Laya.Handler.create(this,function(sp){
                var cube = sp.getChildAt(0);
                cube.transform.translate(new Laya.Vector3(0,3,0));
                this.scene.addChild(cube);
                var cubeCollider = cube.getComponent(Laya.PhysicsCollider);
                var cubeRigid = cube.addComponent(Laya.Rigidbody3D);
				//获取到之前的碰撞盒
                var cubeShape = cubeCollider.colliderShape;
                cubeCollider.colliderShape = null;
                cubeRigid.colliderShape = cubeShape;
            }));
```


Look at the added effect:

![图](img/2.gif)

##### 