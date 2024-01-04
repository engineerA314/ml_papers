https://arxiv.org/abs/2212.03145

FacT: Factor-Tuning for Lightweight Adaptation on Vision Transformer
(Shibo Jie, Zhi-Hong Deng)

Weight 를 Tensorization-Decomposition 해서 Learnable Parameter 수를 더 줄이겠다는 방법.

트랜스포머 전체 Layer 를 Stack 해서 12 * d * d 형태로 만들고, Tensor에 적용할 수 있는 Decomposition 방법을 이용해 Learnable tensor 를 생성.
(FFN 이 크기가 4배이기 때문에 4 + 4 + 1 + 1 + 1 + 1 = 12)

LoRA를 Tensor 로 일반화한 논문. 이렇게 줄인 파라미터 수는 LoRA의 1/4 ~ 1/40 수준.

최종 결과를 보면 데이터셋 1000 개 이하의 low-data regime 에서 Full finetuning 이나 다른 PEFT들보다 효과적이었다고 함.

의문인 건, 이렇게 임의로 weight 를 stack 해도 학습이 잘 되는 지 신기함.

또, MHSA에 적용할 때 효율이 좋았다고 함.
(이는 과거 논문들에서 low budget 에서는 FFN 보다 Attention 에 PEFT 를 적용하는 게 더 효율적이라고 한 발견들과 일치하지만, AdaLora와는 반대되는 결과.)

ViT에 대해 적용한 논문이어서, NLP 영역에 적용할 수 있는지는 확인이 필요.

#peft