AI 스터디 6주차
"Learning Transferable Visual Models From Natural Language Supervision" (2021) - Radford et al



0. **Abstract**
* 고정된 형태의 데이터(정답지 탑재)를 이용해 컴퓨터 비전 모델 학습
-> generality (일반화 성능) \& usability (사용가능성) 제한
-> 해결방안:정답지를 raw text로 대체 -> 추가적인 학습 효과 없이 개선 가능



1. **Introduction and Motivating Work**
자연어 처리 분야: 적은 양의 라벨링된 고품질 데이터 < 다량의 raw text
컴퓨터 비전 분야: 여전히 '적은 양의 라벨링된 고품질 데이터' 사용중
* text로부터 image representation 학습 방법론 연구 많음 -> but 성능 안 좋음
* weak supervision에서 사용은 성능의 향상을 보였다.
* weak supervised 모델과 최근 연구되는 자연어처리를 이용한 image representation 모델과의 차이점은 크기(scale)이다.
* 4억개의 \[이미지, 텍스트]페어 학습-> CLIP(Contrastive Language-Image Pre-training)



2. **Approach**
* 이미지 인코더와 텍스트 인코더를 쌍으로 학습
* 올바른 이미지-문장 쌍의 유사도는 높이고, 틀린 쌍은 낮추는 Contrastive Learning 사용
* 학습 후 텍스트 프롬프트만으로 새로운 분류 가능 (Zero-shot)



3. **Analysis**
* CLIP은  OCR(이미지 속 글자를 컴퓨터가 읽어서 텍스트로 변환하는 기술), 행동 인식, 위치 추정 등 다양한 작업 수행 가능
* 자연어 기반 학습 덕분에 다양한 시각 개념 이해 가능



4. **Data Overlap Analysis**
* 인터넷 데이터 사용으로 평가 데이터셋 중복 가능성 존재
* 중복률 평균은 약 3.2%로 낮음
* 대부분 성능 향상 영향은 0.1% 이하
-> 따라서 CLIP의 성능은 단순 암기가 아니라 실제 일반화 능력 때문이라고 주장



5. **Broader Impacts**
* 사용자가 텍스트만으로 원하는 분류기를 만들 수 있음
* 데이터 라벨링 비용 감소


문제점

* 편향(Bias) 문제 존재
* 특정 인종·성별에 대한 차별 가능성
* 감시·프라이버시 문제 발생 가능성



6. **Limitations**
일부 전문 작업에서는 성능 부족
완전한 SOTA 수준 도달 위해 더 큰 연산량 필요
자연어만으로 복잡한 작업 설명 어려움

7. **Related Work**
이미지와 텍스트를 함께 학습하려는 연구는 이전부터 존재
대표 연구: VirTex, ConVIRT



8\. **적용**

CLIP의 실제 활용 사례:

* 이미지 검색
* 자동 이미지 캡션 생성
* OCR 및 문서 인식
* 자율주행 객체 인식
* 의료 영상 분석 보조
* AI 그림 분류 및 필터링
* 텍스트 입력만으로 새로운 이미지 분류 가능

