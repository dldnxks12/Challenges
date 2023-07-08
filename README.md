### NIPS Challenge code follow ups - `2023/7/8;JS` 

[Home-Robot introduction](https://aihabitat.org/challenge/2023_homerobot_ovmm/)  
[Home-Robot installation guide](https://github.com/facebookresearch/home-robot)


----

- `Task (skills)`


        각 task에 대해 각각 train이 필요
        - Expected tool : [SLAM / Segmentation / RL / Manipulator Control]  

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

- `Info`


        # terminalogy 조심 - 여기서는 task를 state로 표현 
          ex. state      : gaze to object 
              next_state : navigate to object 

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

            *discrete/continuous action setting --> src ~ /core/interfaces.py   

        # Configs :
            Habitat config          : ovmm_eval.yaml
            Agent/Simulation config : yaml files at 'projects/habitat_ovmm/configs/agent'
                (ex. navigation to object agent 설정 수정 -- nav_to_obj_rl.yaml file 에서) 

---

- `baseline demo code`


        *Demo code : projects/habitat_ovmm/eval_baselines_agent.py

        # Env configs - (크게 건드리지 않아도 된다고 가정. 필요할 시, 위 info의 Configs file에서 수정) 
        config_utils.py (get_habitat_config, get_ovmm_baseline_config) 
        omegaconf.py    (DictConfig, OmegaConf)  
    
        # TODO
        [1] ovmm_agent.py (path : src/home_robot/home_robot/agent/ovmm_agent/ovmm_agent.py)
            : Task 수행하는 Agent들 관련  
        [2] evaluator.py  (path : projects/habitat_ovmm/evaluator.py) 
            : episode evaluator 

---

- `TODO (임시)`

    
        #1) ovmm_agent.py의 각 task를 진행하는 agent 수정 
        #2) evaluator.py의 _eval 함수 하단의 TODO - environment parallelize 

    
    

    

    
