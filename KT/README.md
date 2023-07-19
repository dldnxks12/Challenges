### KT Challenge

LLM :
https://arxiv.org/pdf/2302.02662.pdf

Transformer : 
https://arxiv.org/pdf/1706.03762.pdf

GPT :
https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf

---

    # 믿:음 기반 학습 과정
        개발자 중심 -> 데이터 중심 

        1. 학습 데이터     -> LETS에 준비된 도구로 데이터 구축 or 직접 구축 
        2. 준비한 엔진 선택 -> 학습 진행
        3. 자동으로 Inference 해주는 API 생성


        1. 파이프라인 구축에 지니 API 활용가능
        2. 믿:음 모델 자체를 오픈하지 않는다. 
            - 학습 시킬 데이터 준비하고 
            - 학습 파라미터 튜닝해주면서
                
            학습만 해주는 tool을 제공 
        

        # 믿:음을 기반으로한 순차적 의사결정 모델 개발 

        (1)[이미지 -> 해석 -> 텍스트(state) -> 믿음 -> 텍스트(action)] -> (2)[에이전트 - 환경]
        (1) 믿:음 모델 학습 -> (2) 훈련된 믿:음 모델을 통해 순차적 의사결정 모델 학습 

        믿:음으로?  
        현 상황을 파악하는 이미지 해석 모델 개발 
        내가 어느 위치에 있을 때 할 수 있는 행동들을 잘 던져주도록 학습 
    
        믿:음을 통해서 다음과 같은 일을 수행할 수 있다.

        1. 현재 상황을 인식해서 가능한 action들을 던져주기. 
        2. 제안한 각 action에 대한 추천도/신뢰도를 제공하여 각 action에 대한 Q 값에 가중치 형태로 이용  

        
        
        
