https://arxiv.org/abs/2312.13286

Generative Multimodal Models are In-Context Learners
(Quan Sun, Yufeng Cui, Xiaosong Zhang, Fan Zhang, Qiying Yu, Zhengxiong Luo, Yueze Wang, Yongming Rao, Jingjing Liu, Tiejun Huang, Xinlong Wang)

Multi modal LLM 의 사이즈를 키우면 In context learning 이 가능해진다는 것을 보여준 논문.

37B 사이즈의 **Emu2** 를 만드니 ICL 가 나타났음.

특이한 점은, Zero-shot 상황에서는 Emu1, Flamingo 보다 성능이 떨어지지만 4, 8, 16개의 shot 이 주어지면 성능이 상승해서 SOTA를 달성한다는 것.

기존 언어에 대한 ICL이 언어학 이론으로 설명되거나, transformer 로부터 Linear Regression 을 유도해서 설명했었는데, 이런 멀티모달에서까지 나타나는 현상은 어떻게 설명할 수 있을까?

#multimodal #in-context-learning