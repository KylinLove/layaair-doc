#Point Light Introduction

###### *version :2.0.1beta   Update:2019-3-30*

Point Light (Spot Light) est une source de lumière qui émet des rayons dans les quatre coins du monde, également connue sous le nom de lumière omnidirectionnelle ou sphérique.


```javascript

//创建点光源
this.pointLight = this.scene.addChild(new Laya.PointLight());
//设置点光源颜色
this.pointLight.color = new Laya.Vector3(1.0, 0.5, 0.0);
//设置点光源位置
this.pointLight.transform.position = new Laya.Vector3(0.4, 0.4, 0.0);
//设置点光源的范围
this.pointLight.range = 3.0;
```


**Range**Pour définir la plage de sources de lumière ponctuelles, qui correspond à la plage d 'exposition de la lumière ponctuelle, plus la valeur est grande, plus la plage d' éclairage est grande.

Les endroits qui ne sont pas éclairés par la lumière sont noirs en raison de la faible Plage d 'éclairage et du problème de localisation de la source de lumière ponctuelle.

[] (IMG / 1.png) <br > (Figure 1)

