https://arxiv.org/pdf/2303.11366.pdf

Reflexion: Language Agents with Verbal Reinforcement Learning
(Noah Shinn, Federico Cassano, Edward Berman, Ashwin Gopinath, Karthik Narasimhan, Shunyu Yao)

23.12 기준 140회 인용된, Prompt Engineering 계에서는 Baseline 역할을 하는 논문.

GPT 에 Reflexion, 실패를 했을 경우 발생하는 error log 를 LLM을 이용해 자연어 형태의 reflexion으로 만들어 실패 기록과 함께 전달해 재시도를 하면 성능을 끌어올릴 수 있다는 논문.

이를 이용해 HumanEval Code generation 에서 91% Accuracy 로 SOTA 달성. (GPT4 기준 11% 상승)

Code generation 에서는 더 구체적인 error log를 위해서 스스로 test suites 를 만들고 이를 이용해 작성한 코드를 평가하는 방식으로 실험했음.

반 년에 가까운 기간동안 SOTA를 유지한 방법이지만 현재는 MCTS 에 의해 추월당함.

#prompt-engineering #agent