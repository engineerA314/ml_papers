https://arxiv.org/abs/2305.15408

Towards Revealing the Mystery behind Chain of Thought: A Theoretical Perspective
(Guhao Feng and Bohang Zhang and Yuntian Gu and Haotian Ye and Di He and Liwei Wang)

circuit complexity theory 를 이용해, 현실적인 hyperparameter (length, depth, #heads, precision size 등등) 을 가진 Transformer 의 CoT의 작동 원리를 설명한 논문.

    - 만약 CoT를 하지 않는다면(문제에서 바로 정답을 예측하게 한다면) Arithmetic, Equeation Task 에서 Transformer 는 길이 n 이상의 Arithmetic, Equation Task 를 풀 수 없다는 것을 증명
    - 만약 CoT를 할 경우 Depth 4 o5 5, heads=5 일 때 모든 길이 n에 대해 풀 수 있음을 증명
      - 증명 방식은 Transformer components 들로부터 fundamental operations 들을 만들고, 이들로 parralel computing이 가능함을 보여서 증명

기존 연구들은 좀 비현실적인 (infinite 또는 매우 큰) 가정들을 도입해서 Transformer 가 튜링 완전하다던지, universal function approximator라던지 하는 이야기를 했는데,
이 논문은 현실적인 가정에서 실제 모델의 필요 크기를 제시했음.
CoT가 왜 작동하는지에 대한 매우 좋은 설명인 것 같다.

#chain-of-thought
