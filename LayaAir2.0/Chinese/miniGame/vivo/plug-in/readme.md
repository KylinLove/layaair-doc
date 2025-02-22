## LayaAir 2.x - vivo引擎插件使用说明

*IDEversion：2.7.0beta Date：2020-05-21*

#### 1、什么是LayaAir 2.x - vivo引擎插件

vivo小游戏平台，支持公有引擎库以插件的形式，以公共库的形式来使用。

举个例子，如果A、B、C、D、E、F六款游戏，在全都使用LayaAir引擎插件的情况下，如果用户玩了其中任意一款游戏，其它的游戏都不需要再重新下载引擎库部分，只下载自己的项目JS库代码即可。

与从本地包加载引擎的原模式相比，引擎插件模式无疑会增强用户玩游戏时的加载体验。另外，引擎插件的体积并不计入本地包的总体积，相当于节省了大量的引擎库占用空间，让项目可以更重度的发挥。



#### 2、vivo引擎插件支持哪些引擎版本

vivo引擎插件是平台自动识别的。LayaAirIDE发布的时候，会将插件引擎库分离出来，开发者流程上并没有感知。

理论上，可以通过LayaAirIDE发布成为vivo小游戏的各个引擎版本都可以成为引擎插件版本（支持vivo适配之后的都可以，可以查看引擎更新日志）。

这与微信只能使用LayaAir引擎官方上传的小游戏版本方案有所不同。让引擎插件的版本更加自由化，甚至是对官方引擎版本修改过，或者是引擎的beta版，也可以成为插件版本。但是，如果修改了引擎，会导致以下问题：

- 修改引擎后出现BUG的，引擎将不再免费维护。只能视为私有修改版本，只能通过商业合作处理。
- 每一个不同的引擎版本，都会形成一个插件版本，如果你修改了引擎的版本，那么就意味着，你这个引擎插件，只对用了相同库的游戏有效，也就是说你所用的版本，如果没有影响力，那将基本无法享受插件版本的好处，甚至会带来弊端（后面会讲弊端）。因为公有版本的插件成百上千个游戏产品在使用，而你的修改版可能只有自己的公司产品在用。那你自己的产品，可能永远都是第一个下载的，而不是先被下载，无法享受到直接启动已下载的公有插件这个优势。



#### 3、其它的注意事项

- 弊端：使用插件版引擎后，必须要使用LayaAir引擎分离出来的全部引擎库，比如，LayaAir引擎，插件库有6个，即使开发者的项目只用到了3个，那玩家在第一次下载的时候，仍然会下6个。当然，如果你不是插件版本的种子，那就直接使用已下载好的公共的插件版本就好了，无需加载。所以，弊端就是假如你的游戏产品正好是玩家的种子插件，才会遇到。因此，开发者尽量不要去使用beta版这种开发者使用不多的版本作为插件引擎来使用。或者修改引擎包，一旦修改了引擎包，那就不会被识别为LayaAir公有引擎，非常大的概率被识别为插件种子，很难享受无需加载引擎的优势。
- 自2.6.1引擎正式版本开始，默认勾选`是否使用压缩版类库`，也就是说，默认的引擎库就是压缩后的min包，这样可以减少插件种子的加载速度，而且vivo发布为rpk包的时候，还会二次压缩，最终引擎库的体积大概在引擎mini包体积的四分之一左右。所以，建议大家不要取消`是否使用压缩版类库`的勾选。并且一旦取消，也会被判定为，不是公有版引擎，影响插件版本的加载体验。
- 不要改动LayaAir引擎官方提供的版本，尽量注意不要随意打开项目引擎库，对其进行修改。因为对引擎的任何一个文件的改动都可能导致被判定为非公有版本引擎插件，哪怕是一个空格都不行。

