https://arxiv.org/abs/2401.01335

Self-Play Fine-Tuning Converts Weak Language Models to Strong Language Models
(Zixiang Chen, Yihe Deng, Huizhuo Yuan, Kaixuan Ji, Quanquan Gu)

GAN 과 같은 방식의, Self-Play 를 통해 LLM을 학습시키는 방법.
SFT 를 사용하는 경우에는 성능 상승이 멈추고, eval score 가 감소하게 되는데, 이 방법을 사용하면 더 적은 데이터를 사용하고도 더 높은 성능을 낼 수 있다고 한다.

SFT보다 더 global minimum 을 잘 찾을 수 있는 방법이라는 것. 즉 human annotated dataset 이 어느 정도 준비되어 있을 때 최고의 성능을 내기 위한 방법이라고 볼 수 있을 것 같다.

다만 계속해서 성능을 상승시키거나, human annotated dataset 의 필요성을 없애는 방법은 아니다.

수식이 어려운 편이어서, 한 번 더 주의깊게 읽을 예정.

#RL