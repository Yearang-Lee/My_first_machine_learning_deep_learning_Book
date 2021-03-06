# 1. RNN

> - 순차적인 데이터를 입력받아 결괏값을 도출하는 데 사용하는 딥러닝 모델
> - 이전 입력값들을 고려해서 현재 입력값의 출력값을 결정하는 딥러닝 모델
> - 자연어 처리에 많이 쓰임

RNN의 일반적인 구조는 다음과 같다.



네모 박스를 셀이라고 하면

- 현재 셀의 x값과 이전 셀의 h값을 사용해 현재 셀의 h값을 계산

- 현재 셀의 h값 = 현재 셀의 y값 

<img src="/image/3.png"/>

 

h를 결정하기 위해서 두 가지의 가중치가 존재한다.

- 가중치(w)와 편향값(b) :  최초에는 무작위로 부여 => 학습을 통해 최적화  

### 1) 각 출력값에 softmax layer를 연결한 경우

> ex) 단어 품사 분류기 RNN모델
>
> ==> 출력값(y)을 사용한 분류기



<img src="/image/4.png"/>



### 2) 최종 상태값에 softmax layer를 연결한 경우

> ex) 문장의 감정 분석하기 ( 첫 단어부터 마지막 단어까지 읽어보고 감정을 판단해야 하기 때문)
>
> ==> 최종 상태값을 사용한 분류기

<img src="/image/6.png"/>



다음과 같이 한 번에 나타낼 수 있다.

<img src="/image/down.png"/>

<img src="/image/7.png"/>

<img src="/image/5.png"/>



# 2. LSTM

> - RNN의 기본 구조를 그대로 사용하되, 기본 셀 대신 LSTM 셀이 추가된 것
>
> - 예를 들어 문장을 학습한다고 할 때 , 문장이 길어지면 LSTM이 없는 RNN은 성능이 저조함
>
>   - 경사하강법으로 학습을 진행할 때 gradient vanishing/exploding으로 인해 모델 최적화 X
>
>   ===> 이런 문제를 보완하고자 나온 것이 **LSTM **
>
> - 과거의 정보를 기억해서 다음 셀에 활용해 최적의 값을 출력한다.



