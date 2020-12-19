# COMP490 Sem-Eval Task

[Sem-Eval Task Repo](https://github.com/boyuanzheng010/SemEval2021-Reading-Comprehension-of-Abstract-Meaning) <br>
[Experiments Metrics](https://docs.google.com/spreadsheets/d/1pvZ0Beal91XdtRxNQe0eNDgPDkew5T3-iaJOksysZk0/edit?usp=sharing)<br>

---
Axel Bogos - 40077502

To run the baseline, GLoVe `glove.840B.300d.txt` is needed. It can be downloaded [here]( https://nlp.stanford.edu/projects/glove/). 
Note however that there are still unfixed issues in the baseline, see the task repo. 

---

To execute the BERT model (assuming a terminal window opened in the root directory of this repo), this command was used for instance to run sub-task1. Note that manually setting the python path was necessary for me on a remote computer, it might not be needed otherwise. 
```
PYTHONPATH='/home/a_ogos/COMP_490' python ./multiple-choice/run_multiple_choice.py 
--task_name read_comprehension 
--mode sequence-classification 
--model_name_or_path bert-base-uncased
--data_dir ./data/clean_training_data_task3.2 
--do_train 
--do_eval 
--learning_rate 5e-6 
--num_train_epochs 3 
--max_seq_length 80 
--per_device_eval_batch_size=1 
--per_device_train_batch_size=1 
--gradient_accumulation_steps 2 
--eval_steps 100
--logging_steps 100 
--evaluate_during_training 
--output_dir multiple_choice_output 
--logging_dir ./runs 
--overwrite_output 
--warmup_steps 800 
```
