https://arxiv.org/abs/2303.07971

A Theory of Emergent In-Context Learning as Implicit Structure Induction
(Michael Hahn, Navin Goyal)

Grammar formalism 기반으로 ICL의 error bound를 구한 논문.  
    - O(R_n + D[f]) = O(Iteration Complexity(#samples) + Description Length(Task))

CoT에 대해서도 error bound를 구했는데, 일반적인 CoT는 아니고, CoT Prompting에서의 bound를 구했음.  
    - `X_1 F(X_1) G(F(X_1)) X_2` 가 주어졌을 때, `X_1 F(X_1)` 을 이용해 `F(X_2)` 를 구하는 데에 ICL bound 가 적용되고, `X_1 F(X_1)` 를 `Y_1` 라 하고 다시 `Y_1 G(Y_1) Y_2` 형태로 ICL이 별도로 ICL bound 가 적용된다는 것을 보임.

실험적으로 Tree 구조로부터 생성된 Compositional Dataset으로 학습한 ~84M GPT2 가 ICL, CoT Prompting이 가능하다는 것을 확인함.  
-> Pretraining Dataset 을 Compositional 한 Data로 구성하면  
-> Tree parsing 을 통한 Generation이 효율적이어서 GPT가 이렇게 동작하게 되고  
-> Implicit Structure Induction 을 하는 GPT는 ICL과 CoT Prompting 이 가능하다

단, 논문의 이론적 증명 부분은 어렵기도 하지만, Iteration Complexity 에 대한 정의 부분이 불분명한 부분이 있음.
또, CoT를 쓰는 경우는 X-F-G 순서가 항상 반복되기 보다는, 그냥 임의의 inner step 을 생성하면서 성능이 증가하는데, 이 경우에 대한 설명이 되지 않음.
(이 논문에서 설명하는 경우는 3 * 5 + 7 -> 15 + 7 -> 22 가 주어졌을 때, 같은 순서로 5 * 4 + 5 -> 20 + 5 -> 25 를 풀 수 있다는 것)

#in-context-learning
