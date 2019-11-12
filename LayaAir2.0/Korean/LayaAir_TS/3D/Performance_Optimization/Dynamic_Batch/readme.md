#동적 합병

###### *version :2.2.0beta   Update:2019-8-28*

동적 합병**실례 합병**과**정점 합병**두 종류.이 두 가지 최적화는 개발자가 어떤 설정도 하지 않고, 동물체는 동적 이동을 할 수 있으며 제한을 받지 않는다.그러나 합병원칙은 상대적으로 엄격하다.다음은 두 가지 합병의 가장 기본적인 조건이다.

**실행 통합:**

메쉬와 같은 소재 더블 조건이 들어야 합니다.3차원 장면에서 Mesh 와 같은 소재의 모형은 여전히 대량으로 존재할 수 있다. 이때 실제 합병하는 공간이 적지 않다.

**정점 합병:**

소재와 모델 포인트가 10개보다 작아요.정상 합병은 현재 일부 가짜 음영과 특효 모형상 공간을 발휘하고 있다.

**주의:**반투명한 물체는 연속히 보카를 해야 움직임이 합병되기 때문에 반투명물체의 동태 합병 확률이 낮다.