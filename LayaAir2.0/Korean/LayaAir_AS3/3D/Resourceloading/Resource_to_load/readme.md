# 资源加载

###### *version :2.0.1beta   Update:2019-3-19*

자원의 각종 유형을 말하고 우리는 실제 조작으로 이 자원들을 가재한다.본 실례 주소[demo地址](https://layaair.ldc.layabox.com/demo2/?language=ch&category=3d&group=Resource&name=LoadResourceDemo)성

###단일 자원

####1. 장면 가재

싱글 장면을 가재할 때 사용하는 Sce3D.load 방법.


```typescript

//3d场景加载
Scene3D.load("res/TerrainScene/XunLongShi.ls",Handler.create(null,function(scene:Scene3D):void {
    //加载完成获取到了Scene3d
    Laya.stage.addChild(scene);
    //获取摄像机
    var camera:Camera = scene.getChildByName("Main Camera") as Camera;
    //清除摄像机的标记
	camera.clearFlag = BaseCamera.CLEARFLAG_SKY;
    
    //添加光照
    var directionLight:DirectionLight = scene.addChild(new DirectionLight()) as DirectionLight;
    directionLight.color = new Vector3(1, 1, 1);
    directionLight.transform.rotate(new Vector3( -3.14 / 3, 0, 0));
}));
```


복사 후 효과 (그림 1)

[] (img/1.png)<br>(사진 1)

####2. 재질 가재

단독 소재로 가재될 때, 우리가 사용한 Basematerial.load.이번 예에 우리는 스카이 박스가 위에 있는 예시 카메라에 첨부했다.


```typescript

//材质加载		
BaseMaterial.load("res/threeDimen/skyBox/skyBox2/skyBox2.lmat", Handler.create(null, function(mat:BaseMaterial):void {
    //camera.skyboxMaterial = mat;
    //获取相机的天空渲染器
    var skyRenderer:SkyRenderer = camera.skyRenderer;
    //创建天空盒的mesh
    skyRenderer.mesh = SkyBox.instance;
    //设置天空盒材质
    skyRenderer.material = mat;
}));
```


효과를 보다.

[] (img/2.png)<br>(2)

####3. 무늬 가재

테xture2D.load 방법을 단일 텍스처를 다운로드합니다.여기에서 우리는 정방체를 만들고, 가재된 무늬를 그의 무늬로 설정합니다.이 조작은 사실상 3D와 간단한 예시의 동작과 동일한다.


```typescript

//加载纹理
Texture2D.load("res/threeDimen/texture/earth.png", Handler.create(null, function(tex:Texture2D):void {
    //使用纹理
    var earth1:MeshSprite3D = scene.addChild(new MeshSprite3D(PrimitiveMesh.createSphere(5, 32, 32))) as MeshSprite3D;
    earth1.transform.translate(new Vector3(10, 20, -8));

    var earthMat:BlinnPhongMaterial = new BlinnPhongMaterial();
    earthMat.albedoTexture = tex;
    earthMat.albedoIntensity = 1;
    earth1.meshRenderer.material = earthMat;
}));
```


효과 다음과 같습니다 (그림 3):

[] (img/3.png)<br>(2)

####4. 격자 가재

모듈에 사용된 메쉬.load 방법을 단일 게재합니다.


```typescript

//加载Mesh
Mesh.load("res/threeDimen/skinModel/LayaMonkey/Assets/LayaMonkey/LayaMonkey-LayaMonkey.lm", Handler.create(null, function(mesh:Mesh):void {
    var layaMonkey:MeshSprite3D = sprite3D.addChild(new MeshSprite3D(mesh)) as MeshSprite3D;
    layaMonkey.transform.localScale = new Vector3(4, 4, 4);
    layaMonkey.transform.rotation = new Quaternion(0.7071068, 0, 0, -0.7071067);
    layaMonkey.transform.translate(new Vector3(0, 0, 7));
}));
```


완성된 효과를 불러오기 (그림 4):

[] (img/4.png)<br>(4)

####5.가재

단일 미리 설치된 다운로드는 Sprite3D.load 방법을 사용합니다.


```typescript

//加载精灵
Sprite3D.load("res/threeDimen/skinModel/LayaMonkey/LayaMonkey.lh", Handler.create(null, function(sp:Sprite3D):void {
    var layaMonkey2:Sprite3D = scene.addChild(sp) as Sprite3D;
    layaMonkey2.transform.localScale = new Vector3(4, 4, 4);
    layaMonkey2.transform.translate(new Vector3(-10, 13, 0));
}));
```


다운로드 완료 후 효과 (그림 5):

[] (img/5.png)<br>(도 5)

####6. 애니메이션

단일 애니메이션 불러오기, 이번 예례로 사용하는 캐릭터 내보내기 시 애니메이션 메시지가 있는 후 삭제`.lh`파일 중 애니메이션에 관한 정보는 단지 사용을 보여 준다.후기 사용에서 골격 애니메이션을 교체할 수 있다.


```typescript

//加载胖子精灵
Sprite3D.load("res/threeDimen/skinModel/BoneLinkScene/PangZiNoAni.lh", Handler.create(null, function(sp:Sprite3D):void {
    pangzi = scene.addChild(sp) as Sprite3D;
    pangzi.transform.localScale = new Vector3(4, 4, 4);
    pangzi.transform.translate(new Vector3(-20, 13, 0));
    //获取动画组件
    pangziAnimator = pangzi.getChildAt(0).getComponent(Animator) as Animator;
    //AnimationClip的加载要放在Avatar加载完成之后
    AnimationClip.load("res/threeDimen/skinModel/BoneLinkScene/Assets/Model3D/PangZi-Take 001.lani", Handler.create(null, function(aniClip:AnimationClip):void {
        //创建动作状态
        var state1:AnimatorState = new AnimatorState();
        //动作名称
        state1.name = "hello";
        //动作播放起始时间
        state1.clipStart = 0 / 581;
        //动作播放结束时间
        state1.clipEnd = 581 / 581;
        //设置动作
        state1.clip = aniClip;
        //设置动作循环
        state1.clip.islooping = true;
        //为动画组件添加一个动作状态
        pangziAnimator.addState(state1);
        //播放动作
        pangziAnimator.play("hello");
    }));
}));
```


[] (img/6.gif)<br>(도 6)

###대량 추가 자원

위의 예를 들어 Scene.load () 방법은 자원의 비동기 다운로드, 때로는 3D의 자원이 비교적 커서, 다음 화면을 높이는 체험이 필요합니다.이때 우리는 가재기로 선재할 수 있다.

2D 게임 자원은 저희가 쓰고 있습니다.**Laya.loader.load ()**방법 불러오기, 3D 자원은 Laya.loader.create () 를 사용해야 합니다.다운로드 완료 후 우리는 바로 사용할 수 있다**Laya.loader.getRes ()**이 방법은 가재 가능한 자원을 취득할 수 있다.참고해 주세요.[API描述](https://layaair.ldc.layabox.com/api2/Chinese/index.html?category=Core&class=laya.net.LoaderManager).


```typescript

......
//批量预加载方式
public function PreloadingRes() {
    //预加载所有资源
    var resource:Array = ["res/threeDimen/scene/TerrainScene/XunLongShi.ls",
                          "res/threeDimen/skyBox/skyBox2/skyBox2.lmat",
                          "res/threeDimen/texture/earth.png",                      "res/threeDimen/skinModel/LayaMonkey/Assets/LayaMonkey/LayaMonkey-LayaMonkey.lm",
                          "res/threeDimen/skinModel/LayaMonkey/LayaMonkey.lh", 
                          "res/threeDimen/skinModel/BoneLinkScene/PangZiNoAni.lh",
                          "res/threeDimen/skinModel/BoneLinkScene/Assets/Model3D/PangZi-Take 001.lani",];
    Laya.loader.create(resource, Handler.create(this, onPreLoadFinish));
}

public function onPreLoadFinish() {
    //初始化3D场景
    _scene = Laya.stage.addChild(Loader.getRes("res/threeDimen/scene/TerrainScene/XunLongShi.ls")) as Scene3D;

    //获取相机
    var camera:Camera = _scene.getChildByName("Main Camera") as Camera;
    //设置相机清楚标记，使用天空
    camera.clearFlag = BaseCamera.CLEARFLAG_SKY;
    //调整相机的位置
    camera.transform.translate(new Vector3(0, 45, -60));
    camera.transform.rotate(new Vector3(0, 180, 0), false, false);
    //相机视角控制组件(脚本)
    camera.addComponent(CameraMoveScript);

    //添加光照
    var directionLight:DirectionLight = _scene.addChild(new DirectionLight()) as DirectionLight;
    //光照颜色
    directionLight.color = new Vector3(1, 1, 1);
    directionLight.transform.rotate(new Vector3(-3.14 / 3, 0, 0));

    //使用材质
    var skyboxMaterial:BaseMaterial = Loader.getRes("res/threeDimen/skyBox/skyBox2/skyBox2.lmat") as BaseMaterial;
    var skyRenderer:SkyRenderer = camera.skyRenderer;
    skyRenderer.mesh = SkyBox.instance;
    skyRenderer.material = skyboxMaterial;

    //激活场景中的子节点
    (_scene.getChildByName('Scenes').getChildByName('HeightMap') as MeshSprite3D).active = false;
    (_scene.getChildByName('Scenes').getChildByName('Area') as MeshSprite3D).active = false;

    //使用纹理
    var earth1:MeshSprite3D = _scene.addChild(new MeshSprite3D(PrimitiveMesh.createSphere(5, 32, 32))) as MeshSprite3D;
    earth1.transform.translate(new Vector3(10, 20, -8));

    var earthMat:BlinnPhongMaterial = new BlinnPhongMaterial();
    earthMat.albedoTexture = Loader.getRes("res/threeDimen/texture/earth.png") as Texture2D;
    earthMat.albedoIntensity = 1;
    earth1.meshRenderer.material = earthMat;

    //获取Mesh资源
    var mesh:Mesh = Loader.getRes("res/threeDimen/skinModel/LayaMonkey/Assets/LayaMonkey/LayaMonkey-LayaMonkey.lm") as Mesh;
    //为精灵设置Mesh资源
    var layaMonkey:MeshSprite3D = _scene.addChild(new MeshSprite3D(mesh)) as MeshSprite3D;
    layaMonkey.transform.localScale = new Vector3(4, 4, 4);
    layaMonkey.transform.rotation = new Quaternion(0.7071068, 0, 0, -0.7071067);
    layaMonkey.transform.translate(new Vector3(0, 3, 7));

    //使用精灵
    var sp:Sprite3D = Loader.getRes("res/threeDimen/skinModel/LayaMonkey/LayaMonkey.lh") as Sprite3D;
    var layaMonkey2:Sprite3D = _scene.addChild(sp) as Sprite3D;
    layaMonkey2.transform.localScale = new Vector3(4, 4, 4);
    layaMonkey2.transform.translate(new Vector3(-10, 13, 0));

    //使用精灵
    pangzi = Loader.getRes("res/threeDimen/skinModel/BoneLinkScene/PangZiNoAni.lh") as Sprite3D;
    pangzi = _scene.addChild(pangzi) as Sprite3D;
    pangzi.transform.localScale = new Vector3(4, 4, 4);
    pangzi.transform.translate(new Vector3(-20, 13, 0));
    //获取动画组件
    pangziAnimator = pangzi.getChildAt(0).getComponent(Animator) as Animator; 

    var pangAni:AnimationClip = Loader.getRes("res/threeDimen/skinModel/BoneLinkScene/Assets/Model3D/PangZi-Take 001.lani") as AnimationClip;
    //创建动作状态
    var state1:AnimatorState = new AnimatorState();
    //动作名称
    state1.name = "hello";
    //动作播放起始时间
    state1.clipStart = 0 / 581;
    //动作播放结束时间
    state1.clipEnd = 581 / 581;
    //设置动作
    state1.clip = pangAni;
    //设置动作循环
    state1.clip.islooping = true;
    //为动画组件添加一个动作状态
    pangziAnimator.addState(state1);
    //播放动作
    pangziAnimator.play("hello");
}
......
```


효과 보이기:

[] (img/7.png)<br>(7)

**Tips:**프로젝트에서는 일반적으로 우리는 모두 가재기의 방식을 채택하여 자원에 좋은 관리를 할 수 있다.