##버전 관리 기능 소개

![publish](res/publish.png) 


버전 관리에 관해 맨 처음에는 링크 후 랜덤 수를 추가하는 방식으로 관리하고 있지만, 위신 등 환경에서 캐시 문제가 심각하고, 랜덤 수 방식은 캐시 문제를 해결할 수 없으며, 아니면 업데이트 버전으로 페이지 혼란을 초래하는 현상이 나타난다.이에 따라 레이어이더는 발표할 때 캐시 문제를 근본적으로 해결할 수 있는 방안을 늘렸다. 바로 직접 개명 파일 이름도 달라졌고, 캐시 문제가 자연히 존재하지 않는다.

###버전 관리 메커니즘

개발자가 버전 관리를 활성화한 후 발표할 때 hash 문자열의 파일 이름을 자동으로 생성할 것입니다. version.json 파일 이름 맵 파일을 생성합니다.버전 관리를 통해 ResourceVersion 자동 연결 코드의 실제 파일 이름과 이름을 바꾸는 버전 관리 제어 파일입니다.개발자가 버전 관리를 활성화하는 파일이 바뀌면 파일 이름을 자동으로 바꾸는 hash 문자열을 자동으로 업데이트하는 것은 실행환경에서 새로운 파일을 적용하는 데 해당하는 것은 자연히 캐시 파일이 존재하지 않을 것이다.

개발자가 개발하는 과정에서 판본관리가 최종 생성된 파일명을 주목할 필요가 없다.레이레이어이드의 2.0이 프로젝트를 창건할 때 이미 자동으로 코드관리류 Resourceversion, 개발자는 Resourceversion을 어떻게 사용하는지도 주목할 필요가 없다. 버전 관리를 할 때 항목 게시 인터페이스를 적용할 수 있는 옵션을 선택하면 된다.

###버전 관리 효과 사용하기

항목에 인터페이스를 발포하고 버전 관리를 활성화하면 발표할 때 파일 이름에 hash 문자열을 붙여 그림을 그리는 것과 같다.파일이 바뀌면 변경된 파일 이름에 따라 새로운 hash 문자열을 변경합니다.

![图3](res/3.png) 


상도에서 보여준 효과, 왼쪽 은 개발 환경 아래 bin 디렉토리, 오른쪽은 버전 관리 후 발표 디렉토리를 사용하여, js 디렉토리 아래 js 파일과 res 디렉토리 아래 png 이미지 파일 이름으로 hash 문자열에 포함되어 있습니다.