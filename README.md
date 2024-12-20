# REMED
## _Retrieval-Augmented Medical Document Query Responding with Embedding Fine-Tuning_ [[Paper]](https://ieeexplore.ieee.org/document/10651011)
Tianqi Pang, Kehui Tan, Yujun Yao, Xiangyang Liu, Fanlong Meng, Chenyou Fan, Xiaofan Zhang
[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)](https://github.com/Aurora-tq/medical_retrieval/main/LICENSE) 

## DATASET
```sh
MMD- Medical Menu Dataset
MPD- Medical Paper Dataset
```

## Eembedding Model
Modify in 'model/chatglm1_MMD.py'

Change the embedding model according to your needs:
```sh
self.embed_model = SentenceTransformer('your/path/to/moka-ai/m3e-base', device)
```

## Model

Python 'train/run.py'

If you need to change a different model please refer to the following code:

Load chatglm1:
```sh
model =  MyGLU(hidden_size = 768)
model.load_state_dict(torch.load("model/best_chatglm1.ph"))
model = model.to(device)
```

Load chatglm2：
```sh
config = ChatGLMConfig()
model = MyMLP(config)
model.load_state_dict(torch.load("model/best_chatglm2.ph"))
model = model.to(device)
```

## EVAL
Bechmark:M3E(Chinese),E5(English)
```sh
python eval.py
```
## Notes
model: the main model design

train: training with data without label_improved

finetune: training with label_improved data

eval: evaluate the search results of the retriever using evaluation criteria such as accuracy, recall, F1 value, etc.

## Citation
If you are using the data/code/model provider here in a publication, please cite our paper:
```sh
@INPROCEEDINGS{2024pangREMED,
  author={Pang, Tianqi and Tan, Kehui and Yao, Yujun and Liu, Xiangyang and Meng, Fanlong and Fan, Chenyou and Zhang, Xiaofan},
  booktitle={2024 International Joint Conference on Neural Networks (IJCNN)}, 
  title={REMED: Retrieval-Augmented Medical Document Query Responding with Embedding Fine-Tuning}, 
  year={2024},
  doi={10.1109/IJCNN60899.2024.10651011}}
```





