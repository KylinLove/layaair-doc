#VSlider 구성 요소 참조



##1, VSlider 구성 요소 알아보기

###1.1 VSlider 역할과 효과

HSlider 와 VSlider 구성 요소는 모두 Slider 구성 요소의 하위 클래식과 세로 슬라이드사용자는 슬라이더 궤도 사이를 통해 슬라이더를 선택할 수 있다.재생기 진도 제어, 음량 크기 제어, UI 의 수치 조정 등 일반적으로 사용됩니다.

VSlider 구성 요소를 세로 배열합니다.슬라이더 궤도는 위에서 아래로 확장되어 있으며, 수치의 탭은 궤도에 위치한 오른쪽 부분에 보이면 숨길 수 있습니다.



​      ![图片0.gif](img/0.gif)< br >>
(그림 1)



###1.2 VSlider 구성된 피부(skin)규범

VSlider 자원 이름: vsliser 접두사 이름, 기본 자원 총 3개`vslider$bar.png`진도 자원`vslider$progress.png`원도 자원`vslider.png`.

자원은 적어도 두 개, 한 원도 자원, 미끄럼 자원 하나, 그렇지 않으면 미끄럼 기능을 실현할 수 없다.진도 자원 구성 요소가 부족하면 틀림없다. 진도를 표시하지 않을 뿐이다.

진도 자원`vslider$progress.png`원도 자원`vslider.png`교환 후 진도 반전 가능.

![图片0.png](img/1.png)< br >>
(2)



###1.3 VSlider 구성 요소 API 소개

VSlider API 소개 참고해주세요.[http://layaair.ldc.layabox.com/api/index.html?category=Core&class=laya.ui.VSlider](http://layaair.ldc.layabox.com/api/index.html?category=Core&class=laya.ui.VSlider).



##2, LayairierID를 통해 VSlider 구성 요소 만들기

###1.1 VSlider 만들기

자원 패널에 있는 VSlider 구성 자원을 누르고 페이지 편집 영역에 끌면 VSlider 구성 요소를 페이지에 추가할 수 있습니다.

VSlider 가 편집기 영역에 끌려 있는 후 sizegrid 구궁격의 속성을 설정하여 확대 후 늘어뜨리지 않으며 확대 후 크기 조정 후 효과 보이기:

​![图片2.png](img/2.png)< br >>
(2)

###1.2 VSlider 구성 속성

VSlider 구성 요소는 HSlider 구성 요소와 모두 같지만, 구성 요소의 방향에 달라진 것이다.

같은 VSlider 속성 max 값을 20, 속성 min 의 값은 0, 속성 value 의 값을 5로 표시한 후 다음과 같습니다:

​![图片3.png](img/3.png)< br >>
(그림 3)

**max:**VSlider 슬라이더가 가장 오른쪽으로 끌 때 최대 값은 100;

**min:**VSlider 슬라이더가 가장 왼쪽으로 끌 때 최소값, 기본값은 0;

**value:**슬라이더가 현재 위치의 수치는 max 혹은 min, 또는 그것들의 값이다.

​![图片4.png](img/4.png)< br >>
(그림 4)

프로그램에서 실행할 때 슬라이더를 끌 수 있습니다:

​![图片0.gif](img/0.gif)< br >>
(그림 5)



###1.3은 VSlider 로 음량 컨트롤을 제작한다.

게임 개발이나 일부 소프트웨어에서 VSlider 로 음량 컨트롤러를 만드는 것은 흔하다.그러나 5개에 제시한 것처럼 우리가 필요로 하는 효과가 아니라 진도 방향과 크기가 모두 반대로 바뀌었다.정상적인 것은 음량 최대치를 최상부에서 최소값은 최하층으로 해야 하며, 진도 조차도 아래로 바뀌어야 한다.

사실 정상적인 효과는 매우 간단합니다. 우선 max 와 min 속성 을 반대로 설정할 수 있습니다. 예를 들면 max 0, min 은 20, 그리고 value 값은 기본값으로 최대 20으로 설정됩니다.

​![图片5.png](img/5.png)< br >>
(그림 6)

다음은 진도 줄기의 방향으로 진도 자원과 베이스 자원의 명명 교환 (그림 7) 을 새로 고침, ID를 편집한 후 우리는 진도를 볼 수 있는 방향이 아래로 아래로 내려갔다.우리가 필요로 하는 음량 컨트롤러 효과도 달성했다.

​![图片7.png](img/6.png)< br >>
(그림 7)

​![图片7.gif](img/7.gif)< br >>
(그림 7)



###1.4 VSlider 구성 특수 기타 속성

기타 속성 설정기 '속성 설정기' 에 대한 자세한 소개가 있습니다. 다음은 HSlider 구성에 관한 특수 속성입니다.

124대**속성**124대**기능 설명**124대
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
"1244 allowClick Back"의 한 부르 (BallowClick Back) 가 클릭 클릭을 통해 Value (Value) 를 변경할 수 있도록 지정합니다.124대
1, 12444 showLabel (124) 브라르치에서 슬라이드 위쪽에 숨겨진 Value 값을 표시할 지 지정합니다.124대
일렉트로닉 (1244사) 활동조각도 수치는 슬라이더 (Value) 가 매번 끌 때마다 늘어나는 Value 수치를 가리킨다.기본값은 1입니다.124대


 
