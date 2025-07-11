<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://github.com/SkyworkAI/Skywork-R1V/blob/main/imgs/skywork_logo.png" alt="Skywork Logo" width="400">
  <h1><strong>Skywork-R1V3</strong></h1>
</div>

<font size=7><div align='center' >  [[🤗 Skywork-R1V3-38B](https://huggingface.co/Skywork/Skywork-R1V3-38B)] [[📖 R1V3 Report](https://github.com/SkyworkAI/Skywork-R1V/blob/main/Skywork_R1V3.pdf)] </div></font>

Welcome to the Skywork-R1V3 repository! Here, you'll find the model weights and inference code for our state-of-the-art open-sourced multimodal reasoning model by reinforcement finetuning.

## 🔥 News

**July 9, 2025: 💥 We released Skywork-R1V3-38B [[🤗 Skywork-R1V3-38B](https://huggingface.co/Skywork/Skywork-R1V3-38B)], the latest and most powerful open-source multimodal reasoning model in the Skywork series, pushing the boundaries of multimodal and cross-disciplinary intelligence. Mainly through RL algorithm in post-training, R1V3 significantly enhances multimodal reasoning ablity and achieves open-source state-of-the-art (SOTA) performance across multiple multimodal reasoning benchmarks, e.g. 76.0 on MMMU.**

**April 28, 2025**: We released awq quantized version of Skywork R1V2[[🤗 Skywork-R1V2-38B-AWQ](https://huggingface.co/Skywork/Skywork-R1V2-38B-AWQ)], supporting single-card (above 30GB) inference.

 **April 24, 2025**: We released **Skywork-R1V2**, an advanced open-source multimodal reasoning model that demonstrates strong performance across a range of multimodal reasoning benchmarks including MMMU, MMMU-Pro, MathVista, and OlympiadBench.[[🤗 Skywork-R1V2-38B](https://huggingface.co/Skywork/Skywork-R1V2-38B)][[📖R1V2 Report](https://arxiv.org/abs/2504.16656)] 
 
**April 9, 2025**: Our technical report is currently available on arxiv: [[Skywork-R1V: Pioneering Multimodal Reasoning with CoT](https://arxiv.org/abs/2504.05599)].

**Mar 26, 2025**: We released awq quantized version of Skywork R1V[[🤗 Skywork-R1V-38B-AWQ](https://huggingface.co/Skywork/Skywork-R1V-38B-AWQ)], supporting single-card (above 30GB) inference.

**Mar 18, 2025**: We are thrilled to introduce Skywork R1V, the first industry open-sourced multimodal reasoning model with advanced visual chain-of-thought capabilities, pushing the boundaries of AI-driven vision and logical inference! 🚀


## 📊 Evaluation
Skywork-R1V3-38B demonstrates state-of-the-art performance on various multimodal reasoning tasks. We provide the code in [eval](https://github.com/SkyworkAI/Skywork-R1V/tree/main/eval) to reproduce these results.

**Comparison of Skywork-R1V3 with Multimodal Open-Source and Proprietary Models**

<img src="https://github.com/SkyworkAI/Skywork-R1V/blob/main/imgs/r1v3_eval.png?raw=true" width="800"/>

**Performance Overview**

<img src="https://github.com/SkyworkAI/Skywork-R1V/blob/main/imgs/r1v3_eval2.png?raw=true" width="800"/>

 
## 🚀 How to Run Locally

### 1. Clone the Repository

```shell
git clone https://github.com/SkyworkAI/Skywork-R1V.git
cd skywork-r1v/inference
```

### 2. Set Up the Environment

```shell
# For Transformers  
conda create -n r1-v python=3.10 && conda activate r1-v  
bash setup.sh  
# For vLLM/evaluation  
conda create -n r1v-vllm python=3.10 && conda activate r1v-vllm  
bash ./eval/vlmevalkit/build_env.sh
```

### 3. Run the Inference Script

#### Using Transformers
```shell
CUDA_VISIBLE_DEVICES="0,1" python inference_with_transformers.py \
    --model_path path \
    --image_paths image1_path \
    --question "your question"
```
#### Using vLLM
```shell
python inference_with_vllm.py \
    --model_path path \
    --image_paths image1_path image2_path \
    --question "your question" \
    --tensor_parallel_size 4
```

## License
This code repository is licensed under [the MIT License](https://github.com/SkyworkAI/Skywork-R1V/blob/main/LICENSE). 

✅ Commercial use permitted

✅ Modification allowed

✅ Distribution allowed

❌ No liability

This project uses the [InternVL3-38B](https://huggingface.co/OpenGVLab/InternVL3-38B) as the base model, which is licensed under the MIT License.

## Citation
If you use Skywork-R1V in your research, please cite:
```
@misc{shen2025skyworkr1v3technicalreport,
      title={Skywork-R1V3 Technical Report}, 
      author={Wei Shen and Jiangbo Pei and Yi Peng and Xuchen Song and Yang Liu and Jian Peng and Haofeng Sun and Yunzhuo Hao and Peiyu Wang and Jianhao Zhang and Yahui Zhou},
      year={2025},
      eprint={2507.06167},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2507.06167}, 
}
```
```
@misc{chris2025skyworkr1v2multimodalhybrid,
      title={Skywork R1V2: Multimodal Hybrid Reinforcement Learning for Reasoning}, 
      author={Peiyu Wang and Yichen Wei and Yi Peng and Xiaokun Wang and Weijie Qiu and Wei Shen and Tianyidan Xie and Jiangbo Pei and Jianhao Zhang and Yunzhuo Hao and Xuchen Song and Yang Liu and Yahui Zhou},
      year={2025},
      eprint={2504.16656},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2504.16656}, 
}
```

```
@misc{peng2025skyworkr1vpioneeringmultimodal,
      title={Skywork R1V: Pioneering Multimodal Reasoning with Chain-of-Thought}, 
      author={Yi Peng and Peiyu Wang and Xiaokun Wang and Yichen Wei and Jiangbo Pei and Weijie Qiu and Ai Jian and Yunzhuo Hao and Jiachun Pan and Tianyidan Xie and Li Ge and Rongxian Zhuang and Xuchen Song and Yang Liu and Yahui Zhou},
      year={2025},
      eprint={2504.05599},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2504.05599}, 
}
```
