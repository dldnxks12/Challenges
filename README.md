### NIPS Challenge code guidelines

*update - `2023/7/8 : JS` 

---

[Home-Robot introduction](https://aihabitat.org/challenge/2023_homerobot_ovmm/)  
[Home-Robot installation guide](https://github.com/facebookresearch/home-robot)


----

- `Task (skills)`


        아래 task들에 대해 각각의 agent가 존재 (slam_agent, manipulation_agent, navigation_agent, ...)
          - expected [slam / segmentation / RL / manipulator control] skills 
          - API 사용이 가능하다면, 개발해보고자 하는 task에 집중하고 나머지는 task는 API 사용.  

        # Gase
        - Gaze at object           (obj 응시)
        - Gaze at receptacle       (놓을 곳 응시)

        # Navigation 
        - Navigation to object     (go to obj)
        - Navigation to receptacle (go to receptacle)

        # Pick & Plac
        - pick obj                 (obj 잡기)
        - place obj                (obj 놓기 )

---

- `Baseline demo code`


        *Demo code : projects/habitat_ovmm/eval_baselines_agent.py

        # Imported files 
            config_utils.py - Env configs file  : 환경 설정이 필요할 시, 최하단 `Info`의 Configs 파일들에서 수정   
            omegaconf.py    - Env configs file
            ovmm_agent.py
            evaluator.py 
    
        # 먼저 살펴볼 코드 파일 
        [1] ovmm_agent.py / filepath : src/home_robot/home_robot/agent/ovmm_agent/)
            : 각 task에 대한 agent 정의 
        [2] evaluator.py  / filepath : projects/habitat_ovmm/) 
            : evaluator
        [3] ppo_agent.py  / filepath : src/home_robot/home_robot/agent/ovmm_agent/)
            : agent 


---

- `TODO (임시)`

        # 각 코드 파일 내부에 *TODO 지시코드 존재 (- 언급된 것 이외의 코드 파일들에서도 다수 있을 것..)

        1. projects, src 등등 파일 내부에 같은 이름의 폴더, 파일들이 다수 존재 (엄청 헷갈림)
            -> 따라서, 우선 demo 코드의 import file들 기준으로 파악하고 이해하는게 좋을 것 같음.
                  - ovmm_agent.py
                  - evalution.py 
    
        2. ovmm_agent.py의 Agent들 관련해서 개발시킬 부분 찾아 수정/보완
            -> observation / action 의 입출력 관련된 코드 살펴보며 하위 코드 파일 수정/보완
                  - ovmm_perception.py
                  - objectnav_agent.py
                  - ppo_agent.py
                  - ...
  
            -> ppo_agent.py 내부에서 import 하는 agent들 파악
                  src/third_party/habitat-lab/habitat-baselines/habitat-baselines/agents 폴더 내부에
                  simple_agent.py, slam_agent.py, mp_agent.py, ppo_agents.py ... 존재
            
                  * src/home_robot/home_robot/agent 폴더 내부에서 agent들 다수 존재하는데, 
                    demo 코드에서는 다루지 않았음.
            
---

- `Info`

        # observation :
            - robot_head_depth
            - object_embedding
            - object_segmentation
            - joint
            - is_holding
            - relative_resting_position

        # action :
            - arm_action
            - base_velocity
  
        # Configs :
            Habitat config          : ovmm_eval.yaml
            Agent/Simulation config : yaml files at 'projects/habitat_ovmm/configs/agent'
                (ex. navigation to object agent 설정 수정 -- nav_to_obj_rl.yaml file 에서) 

        # terminalogy - 여기서는 task를 state로 표현 
          ex. state      : gaze to object 
              next_state : navigate to object

  
---    
    

    

    
