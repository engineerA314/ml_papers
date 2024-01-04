https://arxiv.org/abs/2310.04406


Language Agent Tree Search Unifies Reasoning Acting and Planning in Language Models
(Andy Zhou, Kai Yan, Michal Shlapentokh-Rothman, Haohan Wang, Yu-Xiong Wang)

LLM inference 에 Monte Carlo Tree Search 를 적용하여, HumanEval Code Generation 에서 94.4% SOTA를 달성한 논문.

Tree of Thought 나 Reasoning Via Planning 과 같은 논문들도 Tree 형태의 구조를 제시했지만, 아예 BackPropagate 되는 Value Net 을 적용해 MCTS 를 한 논문은 이게 최초.
가장 일반화된 형태의 External Feedback 기반의 강화학습 적용이라고 볼 수 있을 것 같다.
(Reflexion은 Full trajectory 기반으로 한 번씩만 학습을 하는 거였고, ToT 같은 경우는 Value net 이 없었다)

다만 Value Net 이 굉장히 나이브한데, LLM으로 그냥 점수를 주었다는 것 같다. 또 Simulation Outcome 에 의한 value backpropagate 도 코드를 보니 나이브하게 룰 기반으로 이루어지는 것 같았다.

또, tree search 를 하기 때문에 진정한 의미의 pass@1 인지는 잘 모르겠다.

#prompt-engineering #agent #RL