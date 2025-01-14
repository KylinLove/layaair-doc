#LayaiarIDE로 AS3 프로젝트 만들기 및 디렉터리 구조

>* author: charley vesion:Layairide 2.0*update:2019-02-18

현재 추천 AS3 개발자는 FlashDevelop 및 플래쉬비더환경 개발 Layair 엔진의 HTML5 항목을 사용합니다.하지만 LayairirIDE 프로젝트를 통해 프로젝트를 만드는 것을 권장합니다. FlashDevelop 또는 FlashBuilder 를 통해 편집을 열기 바랍니다.LayaiairIDE 프로젝트를 통해 기본적으로 명확한 디렉터리 구조를 만들 수 있습니다.다음은 LayairirIDE 도구로 AS3 의 프로젝트를 만들기 시작으로 프로젝트를 만들기 위한 구조를 소개합니다.



##1, 다운로드 및 설치 레이어이드

LayairierIDE 와 Layaiaia 엔진을 사용합니다. 게임에서 임의적으로 위치에 엔진 표시: Powered by Layaiaiair Engine
휴대엔진 표시에 대해서는 무료로 사용할 수 있다. 그렇지 않으면 다운로드 조항의 위신 이차원코드 연락이 비즈니스 지급 허가를 받아야 한다.

조항을 받은 후 해압을 다운로드하면, 아이디는 녹색판으로 설치할 필요가 없다.IDE 에 대한 엔진 버전이 포함되어 있으며, 초과 다운로드할 필요가 없습니다.

LayaiarIDE2.0 다운로드 주소: https://ldc2.layabox.com/layadownload/? type=layaide



##둘째, LayairIDE AS3 프로젝트 만들기

####단계 1:

LayairIDE 열기, 클릭`新建`아이콘이나 텍스트는 그림 1개처럼 새 프로젝트 인터페이스에 들어갈 수 있다.

![图片](img/1.png)  


(그림 1)



####단계 2:

선택`LayaAir 2D示例项目`항목 이름, 프로젝트 경로, 그리고 프로그래밍 언어, 엔진 버전 선택 후 클릭`创建`"새로운 빈 항목을 세울 수 있다.그림 2 개.

![图片](img/2.png) 


(2)

####추가 설정:

이하 두 옵션은 선택할 수 있고 개발자는 이해작용을 하고 스스로 선택할 수 있다.

#####1, 위신/바이두 작은 게임 bin 디렉토리 빠른 디버깅

이 옵션을 선택하면 프로젝트를 생성할 때 위신과 바이두의 작은 게임 프로젝트파일을 프로젝트 디버킷 (bin) 아래에 생성할 때, 위신 또는 바이두 소규모 게임 개발 도구 디버킷을 직접 지정할 수 있습니다.이러한 경우 많은 빈번한 디버깅 시간을 절약할 수 있다. 디버깅 공식 버전은 로컬 가방만 내보내야 하기 때문에 매번 일정한 발표 시간이 필요해 디버깅 개발의 효율에 영향을 미칠 수 있기 때문이다.

#####2, FB/FD 프로젝트 파일 추가

Layaiairide는 없어서는 안 되는 Layaiaia 엔진의 집성 개발 환경이다.하지만 AS3 의 오래된 프로그래밍 프로그래밍에 IDE 코드 작성 패턴은 AS3의 우호도 FlashBuildier (FB) 와 FlashDevelop (FD) 에 비해 AS3 기본적으로 이 선택되어 이 옵션을 선택하면 IDE 프로젝트를 창건하는 동시에 FB 와 FD 프로젝트를 창건할 수 있다.



####절차 3:

"생성" 을 클릭한 후 항목의 구조를 볼 수 있으며, 항목 폴더 구조는 그림 3개처럼 보여 줍니다.

![图片](img/3.png) 

(그림 3)

이로써 우리는 이미 성공적으로 AS3 프로젝트 공사를 세웠다.

*Tips:*

>>Layair 엔진에 처음 접촉한 개발자에게 예제 항목을 만들기 추천합니다. 예시 항목을 통해 전체 항목 구조를 빠르게 파악합니다.물론 개발부터 다른 프로젝트 형식의 창설을 시도할 수 있다.



##프로젝트 구조 소개

다음은 지난 명절에 만들어진 프로젝트 구조를 결합시켜 디렉터리의 역할을 소개한다.

###3.1 프로젝트 디렉터리 설정 (.laya 폴더)


 `.laya`폴더에 저장된 항목은 개발에 실행된 일부 프로필 정보가 그림 4개처럼 보여 준다.

![4](img/4.png) 


(그림 4)

#### `compile.js`파일 소개

`compile.js`gulp 사용자 정의 프로세스 스크립트 파일입니다. 개발자가 gulp 에 익숙하면 수정할 수 있습니다. 그렇지 않으면 여기를 움직이지 마세요.

#### `launch.json`파일 소개

`launch.json`프로젝트의 디버그 디버그 디버그 디버그 디버그 설정과 chrome 브라우저 디버그 설정을 저장했습니다.쉽게 바꾸지 말고 잘못을 고치면 항목의 디버깅에 영향을 줄 것이다.

#### `layajs`과`layajs.exe`파일 소개

`layajs`과`layajs.exe`AS3 컴파일러, layajs mac 환경, layajs. layajs.exe win 환경에 사용됩니다.여러 사람이 개발하는 방식으로 많은 환경혼용에 적합한 환경을 보존하는 것이다.

#### `publish.js`파일 소개

`publish.js`gulp 이 프로젝트 발표한 스크립트 파일, 개발자는 여기를 움직이지 마세요.

#### **기타 설명**

일부 프로필 기본값은 없습니다. 하지만 발표할 때도 레이야의 디렉토리에 저장됩니다.예를 들어 웹판, 위신, 바이두 등 작은 게임을 발표하면 각각 다른 유형마다 다른 json 프로필에 따라 wxgame.json 은 마이크로게임 배포 프로필, bdgame.json

기존 버전의 배포 프로필은 pubset.json 입니다.

이상은 이들 모두의 이해가 좀 있으면 통상 상황에서 개발자는 수정할 필요가 없다.그래서 깊이 이해할 필요는 없다.



###3.2 항목의 출력 디렉터리 (bin)


 `bin`디렉터리가 저장된 것은 현재 항목의 출력 파일이다.제시한 대로.

![图5](img/5.png) 


(그림 5)

이 디렉터리는 프로젝트에서 출력하는 js, HTML, 게임 자원 등 프로젝트를 실행하고, 작은 게임 프로젝트를 만들 때 작은 게임 디버그 항목을 선택하십시오.

기본 라야아 디버깅이나 크로메 디버깅을 할 때 실행된 이 디렉터리의 파일입니다.



###3.3 UI 프로젝트 디렉터리 (laya)

`laya`LayaiairIDE 현재 UI 항목을 저장하는 데 사용됩니다.

![图6](img/6.png) 


(그림 6)

####예.`assets`디렉토리

UI 장면에 필요한 구성 요소 그림, 오디오 파일 등을 저장하는 데 사용합니다.

####예.`pages`디렉토리

IDE 안의 장면, 애니메이션, 미리 설정 파일을 저장하는 데 사용합니다.

####예.`.laya`"파일

디렉터리가 아닌 이 파일을 주의하십시오. 레이레이야의 파일은 레이어이더의 UI 프로젝트 프로필입니다.



###3.4 프로젝트 라이브러리 디렉터리 (libs)

예.`libs`"디렉토리 내에서 항목의 라이브러리 디렉토리를 저장하기 위해 사용된 Layaiair 라이브러리 파일입니다.

AS 언어의 Layaia 엔진 라이브러리 파일의 구체적인 디렉터리가 존재합니다`libs/laya/src`하.7 시에 제시한 바와 같다.

![图7](img/7.png)(그림 7)



###3.5 항목의 원본 디렉터리 (src)

프로젝트에 사용된 소스 코드 파일 (AS3 언어 항목은 as 파일입니다) 기본값은 Src 디렉토리에 저장되어 있습니다.

특별히 얘기해야 할 건...`ui`디렉토리는 IDE 자동으로 생성되었고 개발자는 여기를 바꾸지 말고 바꾸어도 다음에 교체될 것이다.그래서 이 디렉토리에는 자신의 코드를 보관하지 말고, 이미 코드를 수정하지 마라.

다른 개발자는 실제 프로그래밍 디렉터리 구조가 필요합니다.사례 코드 소스 코드 항목 구조는 그림 8개와 같다.

![图8](img/8.png) 


(그림 8)



###3.6 프로젝트 프로필

![图9](img/9.png)  


(그림 9)

####  `项目名.laya` 

그림 9 중`2D_DEMO_190218.laya`LayaiairIDE 프로젝트의 프로젝트파일입니다. 현재 항목의 항목 명칭, 사용된 라이브러리 버전 등입니다.

예를 들어:


```json

{"proName":"2D_DEMO_190218","engineType":1,"proType":0,"layaProType":1,"version":"2.0.0"}
```


#### `项目名.as3proj`

그림 9 중`2D_DEMO_190218.as3proj`파일은 FlashDevelop 프로젝트 프로젝트의 프로필입니다.FlashDevelop 편집기를 사용하여 AS3 프로젝트를 개발할 때, FlashDevelop 도구에서 '파일을 통해' 파일을 통해 '열기' 항목을 찾을 수 있습니다.

#### `.actionScriptProperties`파일`.project`파일

`.actionScriptProperties`파일`.project`파일은 Flash Builder 프로젝트 프로필입니다.Flash Builder 사용 시 메뉴판'파일'-'Flash Builder 프로젝트 가져오기 (LayairIDE) 로 만든 AS3 항목을 도입합니다.

#### `语言版本config.json`

그림 9 중`asconfig.json`IDE 컴파일 정보 저장하고 삭제하지 마세요.



###3.7 게시 목록

게시 디렉토리는 기본적으로 존재하지 않습니다. 게시 단추를 누르고, 발표한 후 대응하는 버전 디렉토리를 생성할 수 있습니다. 그림 10개와 같이 보여줍니다.(전문 발표 기능 문서 소개가 있는데, 여기는 세심하게 말할 수 없습니다)

![图10](img/10.png) 


(그림 10)

그림 10개가 제시한 디렉토리 구조는 바로 대응한 발표 후 버전 디렉터리입니다.



###본편의 끝말

이로써 프로젝트가 생성된 기초 콘텐츠를 소개하고 싶다면 아이디의 소개나 IDE 디자인을 알아보려면 IDE 편을 볼 수 있다.