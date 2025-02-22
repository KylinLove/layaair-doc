# F9！项目设置介绍

>LayaiairierIDE 2.0.1 bate 를 채용하면 최신 LayairIDE, 최신 버전 아이디를 기준으로 다운로드하십시오.

##개술

단축키 F9 는 LayaIDE 최상용, 최상의 기능, Laya 의 개발자도 잘 아는 F9의 중요성을 알지만, 이는 이미 1.0이 개발자들에게 잘 알려졌고, 2.0 엔진에서 F9를 사용하지 않을 수 없다.하지만 Laya 개발자는 F9 의 기능을 잘 모르며, 본편은 소개를 드립니다.(숙련자 는 본 편 을 소홀히 할 수 있다)





###미리 보기 설정

항목이 설정된 첫 페이지는 미리 보기 설정을 위해 시작된 장면 (프로그램이 첫 번째 가재된 장면을 설정하고, 현재 장면을 선택하는 것은 편집기 마지막 초점 장소에서 있는 장면, 그리고 다른 설정은 IDE 의 자동 생성 종류 GameConfig, 수동적으로 이 종류를 수정할 수 있으며, IDE 안에서 설정할 수 있습니다.

[] (img/1.png)



GameConfig 아래와 같이:

[] (img/7.png)

현재 장면을 시작할 경우, Main 종류에서 개발자도 자신의 요구에 따라 기본적인 시작 설정을 사용할 수 있습니다.[] (img/8.png)



###라이브러리 설정

코드 패키지 크기를 줄이기 위해 개발자는 사용된 라이브러리만 도입할 수 있으며, 사용할 수 없는 기능은 더 이상 코드 가방의 크기를 점용할 필요가 없다.

베이스 설정은 매우 흔한 기능으로 Webgl 라이브러리를 선택하면 엔진이 초기화된 Webgl 패턴으로, 반대로 canvas 모드입니다.

다른 유고는 실제 수요에 따라 스스로 취사할 수 있다.만약 선형 라이브러리를 하지 않았다면 유고 기능을 사용하면 틀림없다.



[] (img/2.png)



###세트 설정

이곳은 일반적으로 움직일 필요가 없다. 주로 배포모드로, 작은 게임의 코드 패키지 크기를 줄이기 위해 IDE 통합은 기본 파일 모드;

네 가지 패턴의 차이는 다음과 같다:


 **내장 모드**내장 모드 는 편집기 UI 콘텐츠를 한 장면의 코드 파일로 생성할 수 있으며, 코드 스크립트에 IDE 가 만든 UI 장면을 포함하는 정보가 포함되어 작은 게임과 경게임은 아직 출시되지 않았을 때 js 크기를 고려하지 않고, 정상 개발 h5 의 가장 상용 선택을 할 뿐만 아니라, 비보로 페이지 속도가 가장 빠르다.

**가재 모드**다운로드 모드도 세트를 생성할 수 있다. 다른 UI 데이터 정보는 Ui.json 내로 사용할 때 이 json 을 다운로드해야 한다. 마찬가지로 작은 게임이 없는 시대에는 쓸모가 없고, 장면 정보는 js 가방 크기를 아끼고 작은 게임 4m에 더 많은 공간을 절약할 수 있다.사용 시 자원으로 다운로드할 수 있습니다.

**분리 모드**분리 패턴은 가재 모드 바탕에 마찬가지로 세트를 생성할 수 있지만, 모든 장면을 단독으로 생성할 수 있는 장면 데이터 파일을 따로 다운로드할 때마다 모든 장면을 가재 모드 모드로 다운로드하는 것이다.2.0 이후 작은 게임이나 가벼운 게임을 개발하고 메인 가방의 크기와 가재 속도를 줄이기 위해 사용되는 패턴이다.

**파일 모드**파일 패턴은 2.0특유로, 작은 게임을 개발하기 위해 만든 것이다. 그가 생성되지 않는 경우도 js 가방의 크기를 더 줄일 수 있다. 사용할 때 Sce.load 방식으로 사용할 때 세 가지의 가장 큰 차이를 구분하는 것은 바로, 파일 모드에서 현장의 변량을 직접 호출할 수 없고, getchild 가 취득한 후 조작이 필요하다.앞 세 가지 장면에서는 변수를 성명하고 코드 힌트가 내부의 변수를 직접 조작할 수 있다.



#####주의해야 할 것은 js 언어 개발을 선택할 때, 분리모드와 파일 패턴은 다를 것이 없고, 장면 종류가 없다는 것이다.



[] (img/3.png)



###4、그림 설정

그래픽 설정은 자동 패키지 그림의 규칙을 설정할 수 있으며 디렉터리가 수정되지 않는 것이 좋다.

[] (img/4.png)



###5, 편집 설정

만약 이것은 여러 가지 소개를 하지 않는다

[] (img/5.png)