\#**Attention is all you need(week1-2)**

\##**논문의 의도**
RNN과 CNN을 배제하고 Attention만을 사용하는 단순한 아키텍쳐인 transformer를 제안

\##**이전 모델과의 비교)**
이전 모델들은 encoder-decorder구조를 사용
-> 순차적 진행으로 병렬적 처리 불가

Transformer는 encoder와 decorder모두 6개의 레이어를 쌓아 구성한다.

\##**Transformer**

* 병렬화 용이
* 학습시간 대비 성능 높음
* 일반화 용이

\##**결론)**
Recurrent layer를 완전히 하는 multi-headed self-attention에 기반하는 transformer를 제안

\#**트랜스포머**
= 문장 내 단어들의 관계를 파악해서 이해를 하는 모델
= Attention은 단어 쌍 관계를 통해 중요도 판단

\#**Attention 내부구조**

* Query - 질문(내가 찾는 것)
* Key - 특징(문서 제목)
* value - 실제 정보(문서 내용, 본문)

\-> 얼마나 관련있는 지 계산해서 정보 가져오기
-> Q와 K비교한 후 중요도 높은 V가져오기

\##**Multi-Head Attention**
여러 관점에서의 분석을 위해 동시에 여러 Attention을 돌리는 것

\##Positional Encoding
각 단어에 위치정보 추가
단어 배열 순서를 알 수 있음



\##**최신 기술과의 연계**

* 구글 터보 퀀트 (TuboQuant)
* 현재의 Attention 계산을 유지하며 메모리 저장방식을 개선한 방식
* 메모리 사용량을 최대 6배 줄이고 속도는 8배 빠르게 해줌.
* 기존 문제) 문장이 길어질수록 K, V를 저장해야 해야해서 메모리 병목현상 
* 터보 퀀트는 K, V를 합축하는 것이 포인트
* 현재 상용화 여부 논쟁

