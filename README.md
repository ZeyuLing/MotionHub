# MotionHub Dataset

MotionHub is a unified motion dataset collection spanning multiple domains. All motion sequences are converted into Blender-ready SMPLX-55 npz files (missing hand/head joints use zero SMPL pose coefficients for default pose).

If MotionHub supports your research, please cite both MotionHub and the specific subsets you used.

## Single-Person Text-Motion Subsets

| Subset | Has Hand | Caption Source | Motion Quality | Motion Style | Citation | Notes |
|---|:---:|---|---:|---:|:---:|---|
| [AMASS_SUP](https://1drv.ms/u/c/aa7c4b840465cd9b/IQBLqcoNlekpToWOS-oU-AyMAaY4VnKbWqXtCSgmAs7DE1A?e=AMlOgG) | ✔ | Manual + LLM | Excellent | Diverse (dance/daily/fitness) | [citation](#amass_sup) | Very accurate mocap; no jump/penetration artifacts |
| [CombatMotion](https://1drv.ms/u/c/aa7c4b840465cd9b/IQB0fqEctLIlQoQH4hahbhhHAdDvU2lRkzZUYBCOLecuTvE?e=YSmdg0) | ✘ | Original + LLM | Medium | Game-style actions | [citation](#combatmotion) | Some interpenetration; fast motion may have inaccurate displacement |
| [Fit3D](https://1drv.ms/u/c/aa7c4b840465cd9b/IQAVE9xE8xZyQbOUh1k3DKT4AS3noie_SQcN45E0lL5SA8s?e=8BYm6N) | ✔ | Manual + LLM | Excellent | Fitness actions | [citation](#fit3d) | — |
| [Human36M](https://1drv.ms/u/c/aa7c4b840465cd9b/IQA85TjkhXA2TLFD5XqoROoPAXRgQ0o5M8H12-LvqPm1Qpw?e=jkYACc) | ✘ | Gemini 2.5 Auto | Medium | Daily actions | [citation](#human36m) | Monocular mocap; body via GVHMR, hands via AiOS; overall quality average |
| [HumanAct12](https://1drv.ms/u/c/aa7c4b840465cd9b/IQAYP4jOAFhbQIZ8nAH6gWp2ATJsSH2b3tMjJjy79UdzLLY?e=X66Pte) | ✘ | Original + LLM | Medium | Daily actions | [citation](#humanact12) | IK from HumanML3D related data |
| [HumanSC3D](https://1drv.ms/u/c/aa7c4b840465cd9b/IQDgBjaYSAzYTpp564y3EEI5AUSi9Y2nps_IVRAO8GTsVFY?e=2P0RUN) | ✘ | Manual + LLM | Excellent | Daily actions | [citation](#humansc3d) | — |
| [MotionX++](https://1drv.ms/u/c/aa7c4b840465cd9b/IQB7P2DDrXV4Tp8LUN0qF3_iAfIr8_ny1c4AuXxNQ3W3WDg?e=Dgqdzs) | ✔ | Original + LLM | Medium | Mixed daily/sports | [citation](#motionx) | Mixed sources; some monocular mocap; general quality; some captions automatically extracted by VLM with low relevance |
| [NTURGBD120](https://1drv.ms/u/c/aa7c4b840465cd9b/IQBKDfj5SBlATJc-z8SmSG_oAUG1-B5o4BqHedotWtSYs9Q?e=Zb2TjX) | ✘ | Action labels + LLM | Medium | Daily actions | [citation](#nturgbd120) | Monocular mocap; body via GVHMR, hands via AiOS |
| [PerMo](https://1drv.ms/u/c/aa7c4b840465cd9b/IQBaGEVAleFmR7wcRKftqA0lAYXT8lsQ-QPtkEQkyWQf7m8?e=0RiaqH) | ✔ | Original + LLM | Excellent | Stylized daily | [citation](#permo) | Highly stylized daily actions; high quality; original captions simple templates, rewritten by LLM |
| [Trumans](https://1drv.ms/u/c/aa7c4b840465cd9b/IQA2-JxzDPh-RLuNCzqaLVYZAZqpW-CVzaVIZMMhgxA5iEk?e=Ey5ChY) | ✔ | Original + LLM | Excellent | Daily interaction | [citation](#trumans) | Includes 3D scene and objects provided by source dataset |
| [UESTC](https://1drv.ms/u/c/aa7c4b840465cd9b/IQCfxh6ourAURo5VV4VpGWH6ATp4UaefvkhFfblPd6X4-7U?e=JhZDyU) | ✘ | Action labels + LLM | Medium | Daily actions | [citation](#uestc) | Severe jitter in source; smoothed; overall quality average |

## Two-Person Text-Motion Subsets

| Subset | Has Hand | Caption Source | Motion Quality | Motion Style | Citation | Notes |
|---|:---:|---|---:|---:|:---:|---|
| [CHI3D](https://1drv.ms/u/c/aa7c4b840465cd9b/IQCDdN3nApr6QZ4eYpCyCV9_AQQih8wNzst_obOPJ5x-4Fk?e=mLq3AS) | ✔ | Manual + LLM | Medium | Interaction/Sport | [citation](#chi3d) | Relative position error; overall usable |
| [Hi4D](https://1drv.ms/u/c/aa7c4b840465cd9b/IQB9U-VhKooTTpIoGUclTwwEAb2-dCkp2MRQaXij_IxMFeo?e=VEIrdT) | ✘ | Manual + LLM | Excellent | Close interaction | [citation](#hi4d) | High quality |
| [InterHuman](https://1drv.ms/u/c/aa7c4b840465cd9b/IQDOs47x9YRHSZT4V56E5KkuAfLEOyvrcp72LgkAgTULUSY?e=e410HX) | ✘ | Original/Manual + LLM | Medium | Interaction/Sport | [citation](#interhuman) | Low interaction precision; common penetration; two-person captions decomposed to single via manual+LLM |
| [InterX](https://1drv.ms/u/c/aa7c4b840465cd9b/IQCn2w5gEIMIQ7wdgGsyvA4AASm9a2XRbbqlXkWsQqshzrg?e=MaysDr) | ✔ | Original + LLM | Excellent | Interaction/Sport | [citation](#interx) | High quality |

## Dance Motion Subsets

| Subset | Has Hand | Caption Source | Motion Quality | Style | Citation | Notes |
|---|:---:|---|---:|---:|:---:|---|
| [AIST++](https://1drv.ms/u/c/aa7c4b840465cd9b/IQBbxp39rF4IQKTJ9CXzc1VBAfj8UXVabdabRHZNqnEm5bI?e=21P5IC) | ✘ | Manual + LLM | High | Music dance | [citation](#aistpp) | Minor jumps/penetration; overall high quality |
| [FineDance](https://1drv.ms/u/c/aa7c4b840465cd9b/IQCOociTkjJ4S4qKYIBn6lIpAZ71-kp9H21lt3PgalhjZC8?e=cRRduQ) | ✔ | Manual + LLM | Excellent | Fine-grained dance | [citation](#finedance) | — |

## Speaking Motion Subsets

| Subset | Has Hand | Caption Source | Motion Quality | Style | Citation | Notes |
|---|:---:|---|---:|---:|:---:|---|
| [BEAT v2.0](https://1drv.ms/u/c/aa7c4b840465cd9b/IQB4ehycq-nKRq4FTep7imODAWV_iAzlDTTCNl73qiLQgYM?e=3qIsJC) | ✔ | Manual + LLM | Excellent | Speaking gestures | [citation](#beatv2) | No observable flaws |
| [TED](https://1drv.ms/u/c/aa7c4b840465cd9b/IQCyy30UUzEtTKiJA5SY8pyIAWysFmbXRrOV4uxbXs4E2iA?e=SK6ny9) | ✘ | Gemini 2.5 Auto | High | Speaking/Co-Speech | [citation](#ted) | Monocular mocap; body via GVHMR, hands via AiOS; body quality good; captions auto-extracted by Gemini |

## Full MotionHub Archive

**Download (complete):** https://1drv.ms/f/c/aa7c4b840465cd9b/IgAQ3c9R5qjMSaOpkLTSvhrxAeUxaIxoNUdurK0in-souu0?e=sYWYxO

---

## Citations

<a id="amass_sup"></a>
### AMASS_SUP
```bibtex
@conference{AMASS:ICCV:2019,
  title={{AMASS}: Archive of Motion Capture as Surface Shapes},
  author={Mahmood, Naureen and Ghorbani, Nima and Troje, Nikolaus F. and Pons-Moll, Gerard and Black, Michael J.},
  booktitle={International Conference on Computer Vision},
  pages={5442--5451},
  year={2019}
}
````

<a id="combatmotion"></a>

### CombatMotion

```bibtex
@misc{CombatMotion,
  title={AnimationGPT: An AIGC tool for generating game combat motion assets},
  author={Yihao Liao and Yiyu Fu and Ziming Cheng and Jiangfeiyang Wang},
  year={2024},
  howpublished={\url{https://github.com/fyyakaxyy/AnimationGPT}}
}
```

<a id="fit3d"></a>

### Fit3D

```bibtex
@InProceedings{Fieraru_2021_CVPR,
  author={Fieraru, Mihai and Zanfir, Mihai and Pirlea, Silviu-Cristian and Olaru, Vlad and Sminchisescu, Cristian},
  title={AIFit: Automatic 3D Human-Interpretable Feedback Models for Fitness Training},
  booktitle={CVPR},
  year={2021}
}
```

<a id="human36m"></a>

### Human36M

```bibtex
@article{h36m_pami,
  author={Ionescu, Catalin and Papava, Dragos and Olaru, Vlad and Sminchisescu, Cristian},
  title={Human3.6M: Large Scale Datasets and Predictive Methods for 3D Human Sensing in Natural Environments},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  volume={36},
  number={7},
  pages={1325-1339},
  year={2014}
}
```

<a id="humanact12"></a>

### HumanAct12

```bibtex
@inproceedings{guo2020action2motion,
  title={Action2motion: Conditioned generation of 3d human motions},
  author={Guo, Chuan and Zuo, Xinxin and Wang, Sen and Zou, Shihao and Sun, Qingyao and Deng, Annan and Gong, Minglun and Cheng, Li},
  booktitle={ACM International Conference on Multimedia},
  pages={2021--2029},
  year={2020}
}
```

<a id="humansc3d"></a>

### HumanSC3D

```bibtex
@inproceedings{fieraru2021learning,
  title={Learning Complex 3D Human Self-Contact},
  author={Fieraru, Mihai and Zanfir, Mihai and Oneata, Elisabeta and Popa, Alin-Ionut and Olaru, Vlad and Sminchisescu, Cristian},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={35},
  number={2},
  pages={1343--1351},
  year={2021}
}
```

<a id="motionx"></a>

### MotionX++

```bibtex
@article{zhang2025motion,
  title={Motion-X++: A Large-Scale Multimodal 3D Whole-body Human Motion Dataset},
  author={Zhang, Yuhong and Lin, Jing and Zeng, Ailing and Wu, Guanlin and Lu, Shunlin and Fu, Yurong and Cai, Yuanhao and Zhang, Ruimao and Wang, Haoqian and Zhang, Lei},
  journal={arXiv preprint arXiv:2501.05098},
  year={2025}
}
```

<a id="nturgbd120"></a>

### NTURGBD120

```bibtex
@article{liu2020ntu,
  title={NTU RGB+D 120: A Large-Scale Benchmark for 3D Human Activity Understanding},
  author={Liu, Jun and Shahroudy, Amir and Perez, Mauricio and Wang, Gang and Duan, Ling-Yu and Kot, Alex C},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  volume={42},
  number={10},
  pages={2684--2701},
  year={2020}
}
```

<a id="permo"></a>

### PerMo

```bibtex
@inproceedings{kim2025personabooth,
  title={PersonaBooth: Personalized Text-to-Motion Generation},
  author={Kim, Boeun and Jeong, Hea In and Sung, JungHoon and Cheng, Yihua and Lee, Jeongmin and Chang, Ju Yong and Choi, Sang-Il and Choi, Younggeun and Shin, Saim and Kim, Jungho and Chang, Hyung Jin},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2025}
}
```

<a id="trumans"></a>

### Trumans

```bibtex
@inproceedings{jiang2024trumans,
  title={Scaling Up Dynamic Human-Scene Interaction Modeling},
  author={Jiang, Nan and Zhang, Zhiyuan and Li, Hongjie and Ma, Xiaoxuan and Wang, Zan and Chen, Yixin and Liu, Tengyu and Zhu, Yixin and Huang, Siyuan},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2024}
}
```

<a id="uestc"></a>

### UESTC

```bibtex
@article{ji2019uestc_rgbd,
  title={A Large-scale Varying-view RGB-D Action Dataset for Arbitrary-view Human Action Recognition},
  author={Ji, Yanli and Xu, Feixiang and Yang, Yang and Shen, Fumin and Shen, Heng Tao and Zheng, Wei-Shi},
  journal={arXiv preprint arXiv:1904.10681},
  year={2019}
}
```

<a id="chi3d"></a>

### CHI3D

```bibtex
@inproceedings{fieraru2020chi3d,
  title={Three-Dimensional Reconstruction of Human Interactions},
  author={Fieraru, Mihai and Zanfir, Mihai and Oneata, Elisabeta and Popa, Alin-Ionut and Olaru, Vlad and Sminchisescu, Cristian},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2020}
}
```

<a id="hi4d"></a>

### Hi4D

```bibtex
@inproceedings{yin2023hi4d,
  title={Hi4D: 4D Instance Segmentation of Close Human Interaction},
  author={Yin, Yifei and Guo, Chen and Kaufmann, Manuel and Zarate, Juan Jose and Song, Jie and Hilliges, Otmar},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2023}
}
```

<a id="interhuman"></a>

### InterHuman

```bibtex
@article{liang2023intergen,
  title={InterGen: Diffusion-based Multi-human Motion Generation under Complex Interactions},
  author={Liang, Han and Zhang, Wenqian and Li, Wenxuan and Yu, Jingyi and Xu, Lan},
  journal={arXiv preprint arXiv:2304.05684},
  year={2023}
}
```

<a id="interx"></a>

### InterX

```bibtex
@inproceedings{xu2024interx,
  title={Inter-X: Towards Versatile Human-Human Interaction Analysis},
  author={Xu, Liang and Lv, Xintao and Yan, Yichao and Jin, Xin and Wu, Shuwen and Xu, Congsheng and Liu, Yifan and Zhou, Yizhou and Rao, Fengyun and Sheng, Xingdong and Liu, Yunhui and Zeng, Wenjun and Yang, Xiaokang},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2024}
}
```

<a id="aistpp"></a>

### AIST++

```bibtex
@inproceedings{li2021aistpp,
  title={AI Choreographer: Music Conditioned 3D Dance Generation with AIST++},
  author={Li, Ruilong and Yang, Shan and Ross, David A. and Kanazawa, Angjoo},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2021}
}
```

<a id="finedance"></a>

### FineDance

```bibtex
@inproceedings{li2023finedance,
  title={FineDance: A Fine-grained Choreography Dataset for 3D Full Body Dance Generation},
  author={Li, Ronghui and Zhao, Junfan and Zhang, Yachao and Su, Mingyang and Ren, Zeping and Zhang, Han and Tang, Yansong and Li, Xiu},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2023}
}
```

<a id="beatv2"></a>

### BEAT v2.0

```bibtex
@inproceedings{liu2022beat,
  title={BEAT: A Large-Scale Semantic and Emotional Multi-Modal Dataset for Conversational Gestures Synthesis},
  author={Liu, Haiyang and Zhu, Zihao and Iwamoto, Naoya and Peng, Yichen and Li, Zhengqing and Zhou, You and Bozkurt, Elif and Zheng, Bo},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2022}
}
```

<a id="ted"></a>

### TED

```bibtex
@inproceedings{yoon2019ted_gesture,
  title={Robots Learn Social Skills: End-to-End Learning of Co-Speech Gesture Generation for Humanoid Robots},
  author={Yoon, Youngwoo and Ko, Woo-Ri and Jang, Minsu and Lee, Jaeyeon and Kim, Jaehong and Lee, Geehyuk},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  year={2019}
}
```
