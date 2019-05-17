# - Preprocessing Text

<br>

## 1. 지프의 법칙 (Zipf's law) - empirical

<br>

+ 지프이 법칙에 따르면 어떠한 자연어 말뭉치에 나타나는 단어들은 그 사용 빈도가 높은 순서대로 나열하였을 때, 모든 단어의 사용 빈도는 해당 단어의 순위에 반비례한다.
+ 예를들어, 브라운 대학교 현대 영어 표준 말뭉치의 경우, 가장 사용 빈도가 높은 단어는 영어 정관사 "the"이며 전체 문서에서 약 7%가량 차지하는 것에 비해, "of"는 약 3.5% 가량 차지한다.
+ 참고로 지프의 법칙은 도시의 인구 순위나, 기업의 크기, 소득 순위 등과 같은 언어학과 관련 없는 다른 여러가지 순위에 있어서도 발견된다.
+ 아래 그림을 보면 알 수 있듯이, 가장 빈도수가 높은 단어들은 불용어라고 하여 우리가 넣고자 하는 모델에 전혀 도움이 되지 못하는 feature가 될 것으로 예측할 수 있다.

![image](https://user-images.githubusercontent.com/40786348/57903410-da129300-78a8-11e9-98eb-6db9d1bdb77b.png)

<br>

![image](https://user-images.githubusercontent.com/40786348/57903427-e8f94580-78a8-11e9-9a7c-763a70c4a9a4.png)

<br>
<br>

## 2. 히프의 법칙 (Zipf's law) - empirical 

<br>

+ 코퍼스에서 어휘의 갯수를 M, 토큰의 갯수를 T라고 하면, M = K*T의 b승
+ 보통 영어의 경우 k는 10과 100 사이의 값, b는 0.5 정도로 설정한다. 
+ 양변에 log를 씌우면 선형적인 관계를 갖게 된다.
+ 따라서 히프의 법칙이 보여주는 것은 corpus의 사이즈가 10배 커져도 어휘의 숫자가 10배로 커지지는 않는단 얘기다.

<br>

![image](https://user-images.githubusercontent.com/40786348/57903562-8b192d80-78a9-11e9-8f5d-38913f56cb4b.png)

<br>
<br>

## 3. N-Gram 

<br>

+ count에 기반한 통계적 접근 방법. 모든 단어를 보는 것이 아니라 지정한 n 개수만큼 일부만 고려하는 접근 방법이다.
+ n-gram은 계산한 빈도 수를 바탕으로 확률 값을 추정하고자 하지만, 문장이 길어질수록 코퍼스 내에 그 문장이 존재하지 않을 확률이 높기 때문에 한계점을 지닌다. 코퍼스 내에 없다면 확률 값이 0으로 나올 수 있기 때문이다. 
+ 예를들어, "dog is chasing a lion"과 같은 문장은 corpus 내에 단 한번도 언급되지 않았을 확률이 높기 때문에 계산이 불가능하다. 
+ 영어 같은 경우는 n의 개수가 7만 되도 거의 완벽하게 작동한다고 한다. 
+ n의 개수는 trade-off 관계가 존재한다. n값을 높이면 높일수록 정확도가 떨어진다. 보통 n은 5를 권장한다. 
+ long term dependency를 해결할 방법이 없다. 빈도수가 0이 나오는 특정 부분에 작은 값을 더함으로써 해결하고자 할 수 있지만, 생각해보면 마찬가지로 한계점을 지닌다. 예를들어 똑같이 존재하지 않았던 문장이라 하더라도 "dog is chasing a table" 보다는 "dog is chasing a lion"이 더 그럴듯한 문장이라는 것을 사람은 알기 때문이다.
+ 이 한계점을 극복하고자 neural net based 모델이 나오기 시작했다.

<br>

![image](https://user-images.githubusercontent.com/40786348/57903777-96b92400-78aa-11e9-9502-8d97539d2a40.png)

<br>
<br>

## 4. WPM (Word Piece Model) 

<br>

+ 하나의 단어를 내부 단어 (subword Unit)으로 분리하는 단어 모델


<br>
<br>

## 5. BPE (Byte Pair Encoding) 

+ data 압축의 간단한 형태
+ 자주 등장하는 연속적인 데이터의 byte가 하나의 byte로 대체된다.