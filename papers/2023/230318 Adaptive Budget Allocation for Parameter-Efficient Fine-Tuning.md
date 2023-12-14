https://arxiv.org/abs/2303.10512

Adaptive Budget Allocation for Parameter-Efficient Fine-Tuning
(Qingru Zhang, Minshuo Chen, Alexander Bukharin, Pengcheng He, Yu Cheng, Weizhu Chen, Tuo Zhao)

Layer, submodule 중 task finetuning 에 중요한 위치를 찾아서 이 위치에 PEFT 를 효율적으로 적용하는 방법에 대한 논문.

LoRA Layer AB 를 SVD 해서 PVQ 형태로 사용. (P_1, v, Q_1) 형태의 (row, singular value, column) triplet 에 대해 Importance score 가 높은 triplet 을 남길 때까지 Iteratively pruning을 진행.

Importance score 는 단순히 Singular value의 크기를 사용할 수도 있지만, 보단 triplet 의 parameter 들이 발생시키는 gradient의 크기를 사용했음. (w * delta_w gradient). 또 Stochastic batching 을 고려해서 Smoothing 을 추가.

SVD는 computational cost 가 높기 때문에 P와 Q의 orthogonality 를 강제하는 regularizer 를 사용해서 학습.

결과적으로는 뒤쪽 Layer, FFN의 첫번째 Linear, 그리고 Linear layer in MHSA module 에 많은 수의 triplet이 할당되는 모습을 보임.
이는 기존의 논문들 중 attention layer (특히 Q, K) 가 small budget 에서는 효율적이라는 주장을 반박하는 결과.
또 FFN 의 첫번째 Layer 가 효율적인 것은 LLM이 정보를 FFN 에 key-value pair 형태로 저장한다는 Knowledge Direct Editing 관련 논문들의 결과와 관계가 있어 보임.
(이 이론은 구글에서 반박한 적이 있음.)

기존 LoRA를 Decomposition 해서 low importance row-column tuple 을 제거하는 것은 Orthogonality 가 보장되지 않기 때문에 위험하고, 이 논문의 방법은 상대적으로 안전하다고 주장했음.
(하지만 Pruned LoRA 의 성능이 떨어지기는 하지만 Catastrophic 한 성능 저하가 발생하지는 않아서 Orthogonality 가 중요한 것인지 의심스러움)

가장 의문스러운 것은 triplet 사이의 파라미터 수 차이. FFN triplet 은 MHSA triplet 보다 4배 많은 파라미터를 가지고 있는데, Importance score 가 paramter 수에 대한 평균값으로 계산되었더라도, 더 파라미터 할당량이 많은 선택지가 선택되는 것은 자연스러워 보여서 의문스러움. 물론 FFN_2 는 선택되지 않았기 때문에 괜찮은 것일 수 있다. 만약 괜찮다면 앞으로 모델의 layer, submodule 별 역할과 특징을 알아내는 데에 많이 사용할 수 있을 듯.

#peft #llm-explain