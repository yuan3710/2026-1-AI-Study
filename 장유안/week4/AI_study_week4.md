**AI 스터디 4주차**

**"BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"** 



**기초 개념**

* 파인튜닝: 특정 작업이나 도메인에 높은 적합성을 확보하기 위해, 이미 훈련된 대규모 언어 모델에 특정 데이터셋을 사용하여 추가적인 학습을 수행하는 작업
* state-of-the-art 모델(SOTA): 인공지능(AI) 및 기계 학습(ML) 분야에서 특정 작업에 대해 현재 사용 가능한 최고의 모델 또는 알고리즘



0\. Abstract

* BERT = **B**idirectional **E**ncoder **R**epresentations from **T**ransformers = 트랜스포머의 양방향 인코더 표현
* 새로운 언어 표현 모델(BERT)는 state-of-the-art 모델을 만들기 위해 단 하나의 출력 레이어만 가지고도 파인 튜닝 가능

1\. Introduction

* 언어 모델의 사전 훈련(문장 수준 과제, 토큰 수준 과제)의 2가지 방식
* 특징 기반 접근 방식: 사전 훈련된 표현들을 추가 기능으로 포함
* 파인 튜닝 접근 방식: 최소한의 작업별 매개변수를 도입하고, 모든 사전 훈련된 매개변수를 간단하게 미세조정
* 이전 단방향 방식의 한계:  단방향 방식은 사전 훈련 동안 사용할 수 있는 구조에 한계가 존재함(왼쪽에서 오른쪽으로)
* 양방향 인코딩을 통해 원활한 문맥 파악이 가능(Masked Language Model)
* 좌우의 맥락 융합과 다음 문장 예측이 가능해짐(Next Sentence Prediction)

2\. Related Works

* 2.1 Unsupervised Feature-based Approaches(비지도 특징 기반 접근 방식)

정답 없이 데이터를 특징으로 바꿔서 패턴을 찾는 방법

* 2.2 Unsupervised Fine-tuning Approaches(비지도 미세조정 접근 방식):

정답 없이 이미 학습된 모델을 데이터에 맞게 조금 더 다듬는 방법

* 2.3 Transfer Learning from Supervised Data(지도 데이터로부터 전이 학습): 

자연어 추론과 기계 번역과 같은 대규모 데이터 셋을 사용하여 지도 작업으로부터 효과적인 전이를 보여주는 작업

&#x20;    
3. BERT에 대하여

* transformer 중에서도 encoder부분만을 사용
* 모델 크기에 따라 base 모델(예시: GPT) 과  large 모델 제공
* L = 레이어 개수
* H = 은닉의 크기
* A = 셀프 어텐션 헤드의 수 
* Task1 : Masked LM은 왼쪽과 오른쪽 문맥을 모두 활용하는 양방향 언어 이해를 가능하도록 문장의 일부 단어(약 15%)를 가린 뒤 그 단어를 맞추도록 학습하는 방식. 
* ML 학습 시에는 가린 위치를 항상 \[MASK]로 바꾸지 않고, 80%는 \[MASK], 10%는 랜덤 단어, 10%는 그대로 두어 실제 사용 상황과의 차이를 줄이며,  가려진 단어만 예측하도록 학습.
* Task2: Next Sentence Prediction(NSP)은 두 문장 간의 관계를 이해하도록 하기 위한 사전학습 방식.
* 문장 A 뒤에 문장 B가 실제로 이어지는 문장인지(IsNext) 또는 무작위로 가져온 문장인지(NotNext)를 맞추는 이진 분류 문제로 구성.
* 학습 데이터는 50%는 실제 다음 문장, 50%는 랜덤 문장 -> 모델이 문장 간 의미적 연결을 학습
* BERT의 Fine-tuning : 사전학습된 모델에 작업별 입력과 출력층만 추가한 뒤 전체를 함께 학습하는 방식. 비교적 적은 비용으로 다양한 작업에 빠르게 적용할 수 있다



4\. 적용

* BERT 이후에도 DistlBERT, ALBERT등 BERT보다 경량화 및 최적화된 버전 등장
* 여전히 BERT는 핵심 모델로 사용됨.
* 예) 검색엔진, 챗봇, 자동매칭 고객센터, 감정분석
* 문장 의미 이해해서 결과개선, 키워드 의미 기반 검색, 질문의 의도 및 맥락 파악



