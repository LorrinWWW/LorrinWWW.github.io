---
title: "Jue Wang"
date: 2025-07-01 16:00:00
top: 100
---

Hello, I am currently a senior staff researcher at Together AI, working closely with [Prof. Ce Zhang](https://zhangce.github.io/). Before that, I got my Ph.D. degree from Zhejiang University, advised by [Prof. Lidan Shou](https://person.zju.edu.cn/en/should).

My recent research mainly focuses on efficient and cost-effective algorithms and systems for LLMs:

- Effecient Inference for Language Models
  - [Ladder Residual (ICML25)](https://arxiv.org/abs/2501.06589), [FloE (ICML25)](#), [Self-Spec (ACL24)](https://arxiv.org/abs/2309.08168), [Compress \& Prompt (ICML24)](https://arxiv.org/abs/2305.11186), [Deja Vu (ICML23, Oral)](https://dl.acm.org/doi/10.5555/3618408.3619327), [SkipBERT (ACL22)](https://aclanthology.org/2022.acl-long.503/)
- Efficient Training Systems at Scale
  - [LoRAM (ICLR25)](https://arxiv.org/abs/2502.13533) [CocktailSGD (ICML23)](https://dl.acm.org/doi/10.5555/3618408.3619905), [AQ-SGD (NeurIPS22)](https://proceedings.neurips.cc/paper_files/paper/2022/hash/7a43b8eb92cd5f652b78eeee3fb6f910-Abstract-Conference.html)
- Cost-Effective Algorithms for Enhancing LLMs
  - [MoAA (ICML25)](#), [Mixture-of-Agents (ICLR25, Spotlight)](https://arxiv.org/abs/2406.04692), [Scaling-context (ICLR25)](https://arxiv.org/abs/2504.12637), [Skill-it! (NeurIPS23, Spotlight)](https://arxiv.org/abs/2307.14430)

<!-- My [resume](/about/resume-Jue.Wang.pdf).  -->

## Updates

- May 2025: We got three papers accepted to ICML 2025! Congratulation to the collaborators!
- Jan 2025: We got three papers accepted to ICLR 2025! Congratulation to the collaborators!
- Jun 2024: Check out [Together MoA](https://www.together.ai/blog/together-moa)! Achieving SoTA results with open-source models only.
- May 2024: We had a paper accepted to ACL 2024. Congratulation to the collaborators!
- May 2024: We had a paper accepted to ICML 2024. Congratulation to the collaborators!
- Sep 2023: We had a paper accepted to NeurIPS.
- Aug 2023: [LLaMA-7B-32K](https://huggingface.co/togethercomputer/LLaMA-2-7B-32K) and [LLaMA-7B-32K-Instruct](https://huggingface.co/togethercomputer/Llama-2-7B-32K-Instruct) have been released.
- Jun 2023: [RedPajama-7B-v1](https://www.together.xyz/blog/redpajama-7b) has been released.
- Apr 2023: We got two papers accepted to ICML 2023!
- Mar 2023: [OpenChatKit](https://www.together.xyz/blog/openchatkit) has been released, cheers!
- Nov 2022: Check out our [demo of GPT-JT](https://huggingface.co/spaces/togethercomputer/GPT-JT)!
- Nov 2022: We had a paper accepted to AAAI 2023. Congratulation to the collaborators!
- Nov 2022: Check out our [benchmark](https://nlp.stanford.edu/helm/current/?) on LLMs!
- Sep 2022: We had a paper accepted to NeurIPS 2022. Congratulation and thanks to all the collaborators!
- Apr 2022: We got a paper accepted to IJCAI 2022.
- Mar 2022: I had a visit to ETH Zurich.
- Feb 2022: As the first author, I had a paper accepted to ACL 2022.
- Jun 2021: I graduated from [CentraleSupélec](https://www.centralesupelec.fr/) with diplôme d'Ingénieur (master degree), cheers!
- Dec 2020: As the first author, I had a paper accepted to AAAI 2021.
- Sep 2020: As the first author, I had a paper accepted to EMNLP 2020.
- Apr 2020: As the first author, I had a paper accepted to ACL 2020.

<!---

- Feb 2020: I had a remote internship at [StatNLP](https://statnlp-research.github.io/) under the guidance of [Prof. Wei Lu](https://istd.sutd.edu.sg/people/faculty/lu-wei).
- Aug 2019: I was enrolled in ByteCamp hosted by [ByteDance](https://bytedance.com/en), where I mainly deal with Multimodal Classification.
- July 2019: We got one demo paper accepted to SIGIR 2019. I attended the conference as the assistant presenter.
- Jun 2018 to Dec 2018: I did an internship in [Rokid](https://www.rokid.com/), where I mainly deal with Spoken Language Understanding.
- Jun 2017 to Aug 2018: I did an research internship in [Data Intelligence Lab](http://59.111.103.237:8081/).
--->

## Work Experience

- **Together AI**, Senior Staff Researcher, May 2025 - Now
- **Together AI**, Staff Researcher, July 2023 - May 2025
- **Rokid**, Research Intern, Jun 2018 - Sep 2018

## Education

- **Zhejiang University**, PhD in Computer Science, Sep 2018 - Jun 2023
- **ETH Zurich**, Academic Guest, Mar 2021 - Sep 2021
- **Université Paris Saclay (CentraleSupélec)**, Master (Engineer) in General Engineering, Sep 2016 - Jun 2018
- **Zhejiang University**, Bachelor in Electrical Engineering, Sep 2014 - Jun 2018

## Publications

- [**Ladder Residual: Redefining Tensor Parallelism in Transformers for Accelerated Inference**](https://arxiv.org/abs/2501.06589)
  Muru Zhang, Mayank Mishra, Zhongzhu Zhou, William Brandon, **Jue Wang**, Yoon Kim, Jonathan Ragan-Kelley, Shuaiwen Leon Song, Ben Athiwaratkun, Tri Dao
  Accepted to ICML 2025.
  [\[Paper\]](https://arxiv.org/abs/2501.06589) [\[Code\]](https://github.com/mayank31398/ladder-residual-inference)
- [**FloE: On-the-Fly MoE Inference on Memory-constrained GPU**](https://arxiv.org/abs/2505.05950)
  Yuxin Zhou, zheng li, Jun Zhang, **Jue Wang**, Yiping Wang, Zhongle Xie, Ke Chen, Lidan Shou
  Accepted to ICML 2025.
  [\[Paper\]](https://arxiv.org/abs/2505.05950)
- [**Improving Model Alignment Through Collective Intelligence of Open-Source Models**](https://arxiv.org/abs/2505.03059)
  Junlin Wang, Roy Xie, Shang Zhu, **Jue Wang**, Ben Athiwaratkun, Bhuwan Dhingra, Shuaiwen Leon Song, Ce Zhang, James Zou
  Accepted to ICML 2025.
  [\[Paper\]](https://arxiv.org/abs/2505.03059)
- [**Mixture-of-Agents Enhances Large Language Model Capabilities**](https://arxiv.org/abs/2406.04692)
  Junlin Wang, **Jue Wang**, Ben Athiwaratkun, Ce Zhang, James Zou
  Accepted to ICLR 2025.
  [\[Paper\]](https://arxiv.org/abs/2406.04692) [\[Code\]](https://github.com/togethercomputer/moa)
- [**Scaling Instruction-tuned LLMs to Million-token Contexts via Hierarchical Synthetic Data Generation**](https://arxiv.org/abs/2504.12637)
  Linda He, **Jue Wang**, Maurice Weber, Shang Zhu, Ben Athiwaratkun, Ce Zhang
  Accepted to ICLR 2025.
- [**Train Small, Infer Large: Memory-Efficient LoRA Training for Large Language Models**](https://arxiv.org/abs/2502.13533)
  Jun Zhang, **Jue Wang**, Huan Li, Lidan Shou, Ke Chen, Yang You, Guiming Xie, Xuejian Gong, Kunlong Zhou
  Accepted to ICLR 2025.
- [**Draft & Verify: Lossless Large Language Model Acceleration via Self-Speculative Decoding**](https://arxiv.org/abs/2309.08168)
  Jun Zhang, **Jue Wang**, Huan Li, Lidan Shou, Ke Chen, Gang Chen, Sharad Mehrotra
  In Proc. of ACL 2024.
  [\[Paper\]](https://arxiv.org/abs/2309.08168) [\[Code\]](https://github.com/dilab-zju/self-speculative-decoding)
- [**Compress, Then Prompt: Improving Accuracy-Efficiency Trade-off of LLM Inference with Transferable Prompt**](https://arxiv.org/abs/2305.11186)
  Zhaozhuo Xu, Zirui Liu, Beidi Chen, Yuxin Tang, **Jue Wang**, Kaixiong Zhou, Xia Hu, Anshumali Shrivastava
  In Proc. of ICML 2024.
  [\[Paper\]](https://arxiv.org/abs/2305.11186) [\[Code\]](https://github.com/HazyResearch/skill-it)
- [**Skill-it! A Data-Driven Skills Framework for Understanding and Training Language Models**](https://arxiv.org/abs/2307.14430)
  Mayee F. Chen, Nicholas Roberts, Kush Bhatia, **Jue Wang**, Ce Zhang, Frederic Sala, Christopher Ré
  In Proc. of NeurIPS 2023.
  [\[Paper\]](https://arxiv.org/abs/2307.14430)
- [**CocktailSGD: Fine-tuning Foundation Models over 500Mbps Networks**](https://dl.acm.org/doi/10.5555/3618408.3619905)
  **Jue Wang**$^{\*}$, Yucheng Lu$^{\*}$, Binhang Yuan, Beidi Chen, Percy Liang, Christopher De Sa, Christopher Re, Ce Zhang.
  In Proc. of ICML 2023.
  [\[Paper\]]((https://dl.acm.org/doi/10.5555/3618408.3619905)) [\[Code\]](https://github.com/DS3Lab/CocktailSGD)
- [**Deja Vu: Contextual Sparsity for Efficient LLMs at Inference Time**](https://openreview.net/forum?id=wIPIhHd00i)
  Zichang Liu, **Jue Wang**, Tri Dao, Tianyi Zhou, Binhang Yuan, Zhao Song, Anshumali Shrivastava, Ce Zhang, Yuandong Tian, Christopher Re, Beidi Chen.
  In Proc. of ICML 2023.
  [\[Paper\]](https://openreview.net/forum?id=wIPIhHd00i) [\[Code\]](https://github.com/FMInference/DejaVu)
- [**Holistic Evaluation of Language Models**](https://arxiv.org/abs/2211.09110)
  Percy Liang, Rishi Bommasani, Tony Lee, Dimitris Tsipras, Dilara Soylu, Michihiro Yasunaga, Yian Zhang, Deepak Narayanan, Yuhuai Wu, Ananya Kumar, Benjamin Newman, Binhang Yuan, Bobby Yan, Ce Zhang, Christian Cosgrove, Christopher D. Manning, Christopher Ré, Diana Acosta-Navas, Drew A. Hudson, Eric Zelikman, Esin Durmus, Faisal Ladhak, Frieda Rong, Hongyu Ren, Huaxiu Yao, **Jue Wang**, Keshav Santhanam, Laurel Orr, Lucia Zheng, Mert Yuksekgonul, Mirac Suzgun, Nathan Kim, Neel Guha, Niladri Chatterji, Omar Khattab, Peter Henderson, Qian Huang, Ryan Chi, Sang Michael Xie, Shibani Santurkar, Surya Ganguli, Tatsunori Hashimoto, Thomas Icard, Tianyi Zhang, Vishrav Chaudhary, William Wang, Xuechen Li, Yifan Mai, Yuhui Zhang, Yuta Koreeda.
  TMLR.
  [\[Paper\]](https://arxiv.org/abs/2211.09110) [\[Code\]](https://github.com/stanford-crfm/helm/) 
- [**Effective Continual Learning for Text Classification with Lightweight Snapshots**](https://ojs.aaai.org/index.php/AAAI/article/view/26206)
  **Jue WANG**$^{\*}$, Dajie Dong$^{\*}$, Lidan Shou, Ke Chen, Gang Chen
  In Proc. of AAAI 2023
  [\[Paper\]](https://ojs.aaai.org/index.php/AAAI/article/view/26206)
- **[Fine-tuning Language Models over Slow Networks using Activation Compression with Guarantees](https://proceedings.neurips.cc/paper_files/paper/2022/hash/7a43b8eb92cd5f652b78eeee3fb6f910-Abstract-Conference.html)**
  **Jue Wang**$^{\*}$, Binhang Yuan$^{\*}$, Luka Rimanic$^{\*}$, Yongjun He, Tri Dao, Beidi Chen, Christopher Re, Ce Zhang.
  In Proc. of NeurIPS 2022.
  [\[Paper\]](https://proceedings.neurips.cc/paper_files/paper/2022/hash/7a43b8eb92cd5f652b78eeee3fb6f910-Abstract-Conference.html) [\[Code\]](https://github.com/DS3Lab/AC-SGD)
- **[SkipBERT: Efficient Inference with Shallow Layer Skipping](https://aclanthology.org/2022.acl-long.503/)**
  **Jue Wang**, Ke Chen, Gang Chen, Lidan Shou, and Julian McAuley.
  In Proc. of ACL 2022.
  [\[Paper\]](https://aclanthology.org/2022.acl-long.503/) [\[Code\]](https://github.com/LorrinWWW/SkipBERT)
- [**Continual Federated Learning Based on Knowledge Distillation**](https://www.ijcai.org/proceedings/2022/0303)
  In Proc. of IJCAI 2022.
  [\[Paper\]](https://www.ijcai.org/proceedings/2022/0303)
- **[Effective Slot Filling via Weakly-Supervised Dual-Model Learning](https://ojs.aaai.org/index.php/AAAI/article/view/17643)**
  **Jue Wang**, Ke Chen, Lidan Shou, Sai Wu, and Gang Chen.
  In Proc. of AAAI 2021.
  [\[Paper\]](https://ojs.aaai.org/index.php/AAAI/article/view/17643) [\[Code\]](https://github.com/LorrinWWW/weakly-supervised-slot-filling) [\[Video\]](https://slideslive.com/38948796/effective-slot-filling-via-weaklysupervised-dualmodel-learning)
- **[Two are Better than One: Joint Entity and Relation Extraction with Table-Sequence Encoders](https://aclanthology.org/2020.emnlp-main.133/)**
  **Jue Wang** and Lu Wei.
  In Proc. of EMNLP 2020.
  [\[Paper\]](https://aclanthology.org/2020.emnlp-main.133/) [\[Code\]](https://github.com/LorrinWWW/two-are-better-than-one) [\[Video\]](https://slideslive.com/38939302/two-are-better-than-one-joint-entity-and-relation-extraction-with-tablesequence-encoders)
- **[Pyramid: A Layered Model for Nested Named Entity Recognition](https://aclanthology.org/2020.acl-main.525/)**
  **Jue Wang**, Lidan Shou, Ke Chen, and Gang Chen.
  In Proc. of ACL 2020.
  [\[Paper\]](https://aclanthology.org/2020.acl-main.525/) [\[Code\]](https://github.com/LorrinWWW/Pyramid) [\[Video\]](https://slideslive.com/38929230/pyramid-a-layered-model-for-nested-named-entity-recognition)


## Contact

251 Rhode Island St,

Together AI, San Francisco, CA 94103

Email: zjuwangjue@gmail.com
