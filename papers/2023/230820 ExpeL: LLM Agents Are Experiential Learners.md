https://arxiv.org/abs/2308.10144

ExpeL: LLM Agents Are Experiential Learners
(Andrew Zhao, Daniel Huang, Quentin Xu, Matthieu Lin, Yong-Jin Liu, Gao Huang)

학생이 시험 공부를 하는 과정을 모사해서, LLM이 이전 학습 경험으로부터 Self Prompt Tuning 을 해서 스스로 성능이 증가하도록 만든 논문.

Train time 에는 Reflexion 을 이용해 성공할 때까지 시도하고,
성공한 경험 N(실험에서는 8개 사용)개를 묶어 LLM에게 Insight 를 추출하거나, 같은 example 에 대한 성공-실패 pair 을 묶에 Insight 를 추출.

Test time 에서는 추출된 Insight 들과 RAG Few-shot 을 주어서 딱 1번한 Inference.

다른 성능을 올리는 Prompt Engineering 기법들은 pass@1 이라고는 하는데, 실제로 보면 retry 를 여러 번 하거나, 병렬적인 inference 들을 돌려서 vote, tree search 를 하거나, 아예 따로 학습시킨 작은 모델과 협업하는 방식이어서 좀 억지라는 생각을 했는데, 이 방법은 정말 정직한 pass@1 인 것 같다.

논문에서는 Webshop, Textworld, HOTPOT QA 에서만 실험했지만, 개인적으로 HumanEval Code generation에 적용해본 결과 기존 GPT4 대비 성능이 7% 가량 상승하는 것을 확인했음.

Graidient Descent 없는 모델 학습이 가능할 수도 있을 것 같은데, 얼마나 효율적일지는 모르겠다. 데이터셋을 모으기 힘든 분야에 대해서는 적용해볼만 하지 않을까?

#agent #prompt-engineering