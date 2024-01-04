https://arxiv.org/abs/2307.06949

HyperDreamBooth: HyperNetworks for Fast Personalization of Text-to-Image Models
(Nataniel Ruiz, Yuanzhen Li, Varun Jampani, Wei Wei, Tingbo Hou, Yael Pritch, Neal Wadhwa, Michael Rubinstein, Kfir Aberman)

Stable diffusion 의 DreamBooth 라는 finetuning 방법은 [개인 이미지 + 설명] 을 새로운 "고유 식별자 V" 로 모델에 넣어 모델을 개인화할 수 있음.

이 논문은 이 dreambooth의 파인튜닝 속도를 올리기 위해 하이퍼네트워크로 초기값을 예측

dreambooth 로 파인튜닝되는 파라미터를 2중으로 분해된 lora layer 를 사용해 파라미터 수를 크게 줄임 (중요) = **ightweight DreamBooth (LiDB)**

즉 LoRA를 W=AB 형태가 아니라, W=AXYB 형태로 쪼개고, XY만 학습한 것.
이 때 A와 B를 Orthogonal 하게 Fix.

구체적인 수치는 n*a, a*r, r*b, b*m 에서,
n, m = 1000,
a = 100, b = 50 으로 Learnable Parameter를 Full Finetuning 대비 0.01%, LoRA 대비 약 7.5% 로 줄임.

LLM에 적용할 수 있을까? 얼굴에 대한 개인화처럼, Personalized chatbot 을 만든다면, User 개인정보에 대한 개인화 같은 것에 적용해서 모델의 지식을 매우 조금 정확하게 수정할 수 있지 않을까?

#peft