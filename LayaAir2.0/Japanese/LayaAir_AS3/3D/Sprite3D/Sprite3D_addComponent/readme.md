#Sprite 3 Dはコンポーネントまたはスクリプトを追加します。

###### *version :2.0.1beta   Update:2019-4-13*

**Component**コンポーネントは、すべての3 Dオブジェクトに付加されたコンテンツのベースクラスである。物体にコンポーネントを追加するには、物体の使用が必要です。`addComponent`方法。

！[](img/1.png)<br/>(図1)

**Script 3 D**これは3 D世界のシナリオで、コンポーネントから引き継ぐコンポーネントの一つです。クラスは「抽象クラス」と定義され、インスタンスは許されない。このクラスは一連の虚法を提供する。詳細な使用はAPIで確認できます。[地址](https://layaair.ldc.layabox.com/api2/Chinese/index.html?category=3D&class=laya.d3.component.Script3D)）3 D世界の開発においては脚本類が多く使われていますが、このモジュールは後のシナリオ編で詳しく解説されています。本編では、スピリット3 Dにスクリプトを追加する方法を簡単に解説しています。

以下のコードは公式の例から来ています。[demo地址](https://layaair.ldc.layabox.com/demo2/?language=ch&category=3d&group=Sprite3D&name=ScriptSample)を選択します。

>メインクラス:
>


```typescript

public function ScriptSample() {
    //初始化引擎
    Laya3D.init(0, 0);
    Laya.stage.scaleMode = Stage.SCALE_FULL;
    Laya.stage.screenMode = Stage.SCREEN_NONE;

    //预加载所有资源
    var resource:Array = ["res/threeDimen/skinModel/LayaMonkey/LayaMonkey.lh"];
    Laya.loader.create(resource, Handler.create(this, onComplete));
}

private function onComplete():void {
    //记载场景
    var scene:Scene3D = Laya.stage.addChild(new Scene3D()) as Scene3D;

    //加载相机
    var camera:Camera = scene.addChild(new Camera(0, 0.1, 100)) as Camera;
    camera.transform.translate(new Vector3(0, 0.8, 1.5));
    camera.transform.rotate(new Vector3(-15, 0, 0), true, false);

    //创建平行光
    var directionLight:DirectionLight = scene.addChild(new DirectionLight()) as DirectionLight;
    directionLight.color = new Vector3(0.6, 0.6, 0.6);

    //加载精灵
    var monkey:Sprite3D = Loader.getRes("res/threeDimen/skinModel/LayaMonkey/LayaMonkey.lh");
    //精灵添加脚本
    monkey.addComponent(MonkeyScript);
    scene.addChild(monkey);
}
```


>スクリプトクラス:このスクリプトを追加したオブジェクトを回転させます。
>


```typescript

import laya.d3.component.Script3D;
import laya.d3.core.Sprite3D;
import laya.d3.math.Vector3;

class MonkeyScript extends Script3D {
	private var rotation:Vector3 = new Vector3(0, 0.03, 0);
	
	override public function onAwake():void {
		trace("onAwake");
	}
	
	override public function onStart():void {
		trace("onStart");
	}
	
	override public function onUpdate():void {
		(owner as Sprite3D).transform.rotate(rotation, false);
	}
	
	override public function onLateUpdate():void {
		trace("onLateUpdate");
	}
}

```


このようにスクリプトを追加しました。実行後の効果を確認できます。

！[](img/2 gif)<br/>(図2)
