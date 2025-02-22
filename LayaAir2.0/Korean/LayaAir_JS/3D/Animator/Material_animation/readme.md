#재질 애니메이션 사용

###### *version :2.1.0beta   Update:2019-6-13*

소재 애니메이션은 소재를 바꾸는 색상과 스티커로 애니메이션.

3차원 소프트웨어에서는 3ds max 중에서 재질 관련 애니메이션을 만들 수 있지만 FBX 형식으로 내보내면 유닛은 인식할 수 없고 Layair 3D 엔진이 식별된 소재 애니메이션이 나올 수 없다.따라서 게임 모형 소재 애니메이션은 유닛에서 제작해야 일부 설정을 내보내야 Layair 3D 엔진을 사용할 수 있다.

다음은 네온사인 소재 애니메이션(도1)효과로 유네티에서 애니메이션 만들기 및 사용법을 작성하고 단계는 다음과 같다.

[] (img/1.gif)<br>(1)

####재질 종류 수정

유닛에서 큐브를 끌어 소재를 수정합니다.

[] (img/2.png)<br>(2)

####재질 애니메이션 만들기

1. 소재 유형을 수정한 뒤 애니메이션 모델을 만들어 메뉴 표시줄 윈도우 하에 애니메이션 편집 인터페이스를 열어 단축키 Ctrl+6.

2, create 단추를 누르고 애니메이션 만들기, 이 상자에서 이름을 짓는 기본 이름 New Animation, 저장한 후 자원 관리자에서 애니메이션 파일을 생성할 수 있습니다.

3. 시간축을 선택하는 시간, 재질의 만반사 색상을 수정하고, 반복 작업은 몇 가지 색상을 조정한다.

4, 애니메이션 프레임 수정 곡선 변화, 기본 선형 슬라이드 애니메이션, 우리의 애니메이션 수요에 부합되지 않고, 변량 변화, 재질 애니메이션 수요에 따라 완성.물론 흐르는 물과 구름이 떠다니는 애니메이션을 만들어야 선형 변화 방식을 만들 수 있다.

[] (img/3.png)<br>(2)

####애니메이션 컨트롤러 만들기

이전 애니메이션 컨트롤러와 같이 자원 관리자의 오른쪽 단추를 누르고 애니메이션 컨트롤기를 만들기 위해 Cube 1, 2번 클릭을 한 단계 열어 만든 애니메이션 파일 New Animmation을 애니메이션 컨트롤에 끌어 넣으면 됩니다.

모형을 선택하면 애니메이션 컨트롤러를 모형으로 끌어들이는 애니메이션 구성 요소에서 유닛을 누르면 애니메이션이 우리의 수요에 따라 방영되는 것을 볼 수 있다.

[] (img/4.gif)<br>(4)

####애니메이션 자원 내보내기

유닛에서 애니메이션 편집, 레이야아 플러그인을 사용하여 장면을 내보내는 유형입니다. ls 자원을 내보내지 않았다면 자원 카탈로그에 자원 디렉토리 아래에 직접 사용할 수 있습니다.`Scene3D.load()`방법 불러오기 또는 미리 불러오기.

이하 코드를 참고하여 변색이 너무 느리기 때문에 속도를 조정하였습니다.


```typescript

//加载场景
Laya.Scene3D.load("res/threeDimen/scene/materialScene/Conventional/layaScene.ls", Laya.Handler.create(this, function(scene) {
    Laya.stage.addChild(scene);
    var camera = scene.getChildByName("Main Camera");
    camera.addComponent(CameraMoveScript);
}));

```


