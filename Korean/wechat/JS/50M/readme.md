# 微信小游戏的50M物理缓存管理

> author: charley

###물리 캐시

마이크로폰은 로컬 가방을 제외한 개발자가 50m의 물리 캐시 공간을 이용할 수 있다.최초 게재된 뒤 물리 캐시 자원, 원격 동태를 적용하지 않고 로컬 캐시 자원을 직접 사용하면 된다.이처럼 게이머들은 다운로드 유량을 많이 절약하고 원생 APP 게임처럼 열렸다.



###Layair 엔진 기본 캐시 관리 메커니즘

Layair 엔진에서 엔진은 자동으로 개발자에게 캐시 관리의 메커니즘을 완성하였고, 기본값은 자동 캐시 메커니즘이다.

자동 캐시 모드 아래**자원이 로컬 캐시 되지 않았다면 원격의 자원을 자동으로 캐시 하기 시작한다.주의해야 할 것은 자동캐시 모드에서 캐시 그림과 소리 파일만 저장하는 것이다**다른 형식의 파일이 캐시 파일이 필요하다면 수동 캐시 인터페이스를 통해 다운로드하고 캐시 메모를 할 수 있습니다.

캐시 파일이 50m를 넘으면 자동으로 가장 빠른 캐시 내용을 정리하고 5M의 공간을 정리할 때마다 순환적으로 쓰기, 캐시 메모리에 저장하는 영원한 50m입니다.



###Layair 엔진 수동 관리 캐시 인터페이스

####1. 자동 캐시 취소

만약 게임이 자주 사용하는 자원이 50m보다 크다면 자동관리캐시 파일을 사용하여 개발자의 예상에 도달할 수 없을 것이다.특히 초기 가재된 자원은 상용자원이라면 뒤에 게재된 자원 캐시 50m를 초과하면 초기 캐시 캐시 자원 청소를 할 수 있다. 다음에 사용할 때 다시 한 번 재가해야 한다.그래서 항상 자원이 50m보다 많을 때 개발자는 스스로 어떤 자원 캐시 캐시 보다 더 큰 의미를 가지고 사용자 체험에 더 좋다.이때 자동캐시 모드를 취소할 수 있다.

엔진이 자동으로 관리되지 않으면 MiniAdpter.autoCacheFile 를 false 로 설정할 수 있습니다.필요한 것은 자동캐시 닫힌 후 자동으로 청소하지 않기 때문에 50m이 넘는 후에는 캐시 파일을 작성할 수 있기 때문에 캐시 책략을 잘 세워야 하며 어떤 파일이 캐시 처리해야 할지 결정합니다.



####2, 수동 다운로드 및 캐시

자동 캐시 기능을 사용하지 않기 위해 자동캐시 모드에서 캐시 재생된 json 등 자동캐시 캐시 캐시 캐시 파일을 사용하지 않을 때 downLoadFile 방법을 사용하여 대상 파일을 다운로드하고 버틸 수 있습니다.


```javascript

/**
* 下载文件 
* @param fileUrl 文件地址(全路径)
* @param fileType 文件类型(image、text、json、xml、arraybuffer、sound、atlas、font)
* @param callBack 文件加载回调,回调内容[errorCode码(0成功,1失败,2加载进度)
* @param encoding 文件编码默认 ascill，非图片文件加载需要设置相应的编码，二进制编码为空字符串
*/             
public static function downLoadFile(fileUrl:String, fileType:String = "",callBack:Handler = null,encoding:String = "ascii"):void
```




####3. 캐시 파일 삭제

마이크로폰 캐시 상한은 50M 물리 공간이기 때문에 자동관리캐시 캐시 캐시 캐시 캐시 캐시 캐시 캐시 캐시 캐시 보관을 하든 상한에 도달하면 캐시 캐시 처리가 필요하다.매번 캐시 크기의 기본값은 5M입니다. 캐시 클립을 바꾸려면, 수정을 통해

미니에이드 pter.minClearsize 속성이 가능합니다.

지정한 캐시 파일이나 모든 캐시 파일을 삭제하려면 remove 또는 removeAll 방법을 사용할 수 있습니다.


```javascript

/**
* 删除指定缓存文件
* @param fileUrl文件路径(绝对地址)
* @param callBack 删除回调函数
*/
public static function remove(fileUrl:String,callBack:Handler):void {}
```



```javascript

/**
* 清空缓存空间全部文件内容 
*/  
public static function removeAll():void{}
```




이 문서에 의문이 있다면 공식 홈페이지 커뮤니티에 질문해 커뮤니티의 링크를 공식 QQ 군에 보낼 수 있습니다 @ 관리자 charley

커뮤니티 사이트: https://ask.layabox.com/



##본문 칭찬

만약 본문은 당신에게 도움이 된다고 생각하시면, 스코드가 작가님을 환영합니다. 당신의 격려는 우리가 더 우수한 문서의 동력입니다.

![wechatPay](../../../wechatPay.jpg)