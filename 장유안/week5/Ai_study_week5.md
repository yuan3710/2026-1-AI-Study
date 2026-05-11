AI 스터디 5주차

Denoising Difussion Probabilistioc Models



**Background**

* Diffusion model: parameterized Markov chain을 학습시켜 유한 시간 후에 원하는 데이터에 맞는 샘플을 만드는 모델
* 기존 diffusion 모델 (GAN, VAE)의 문제점 : 고품질의 샘플을 만들기 어려움
* GAN → 이미지 품질은 좋지만 학습이 불안정
* VAE → 안정적이지만 이미지가 흐림



**DDPM**

* Forward process = Markov chain이 점진적으로 noise를 추가 -> 최종적으로 가우시안 noise로 만듦.

&#x09;노이즈를 점차 추가한 끝에 완전히 망가진 형태 출력

* reverse process = gaussian noise로부터 점진적으로 noise를 제거 -> 최종적으로 원하는 데이터에 맞는 샘플 생성

&#x09;반대로 망가진 형태를 점차 걷어내는 과정



즉, 정방향으로 gaussian noising을, 역방향으로 denoising을 학습한다.



**Markov chain(마코프 체인)?**

* 여러 상태들에 주어진 조건부 확률분포에 따라 매 턴마다 상태들 사이를 이동하는 것
* 0번째 부터 t번쨰의 데이터가 존재할 떄, t+1번째는  t번쨰 데이터에게만 영향을 받는다.
* 미래는 오직 직전의 과거에만 영향을 받는다.



**DDPM과 딥페이크**

* 고품질 딥페이크 생성: 

DDPM은 정교한 딥페이크 영상을 생성하는 데 활용됨.

특히 얼굴 정보를 보존하면서 표정이나 조명을 조절가능해 더 정교한 영상 제작 가능



* 실용성 향상: 

DDPM의 느린 생성 속도를 개선한 DDIM(Denoising Diffusion Implicit Models)이 도입

10\~100배 빠른 속도로 고품질 딥페이크 생성이 가능해짐.



* 탐지 기술의 변화: 

DDPM 기반의 딥페이크는 기존의 CNN 기반 탐지기로 구분하기 어려움.

이를 탐지하기 위해 노이즈 생성 패턴을 분석하는 새로운 탐지 기술이 연구 중에 있음



* 윤리적 문제: 

고성능 생성 모델의 발전으로 딥페이크를 통한 데이터 프라이버시 침해, 가짜 뉴스 생성 등 윤리적 위협

을 경계해야함.







&#x20;	

