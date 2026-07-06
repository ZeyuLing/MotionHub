---
license: other
task_categories:
- other
tags:
- motion
- smpl-h
- smplh
- motionhub
- text-to-motion
- motion-to-text
- music-to-dance
- speech-to-gesture
- human-motion
pretty_name: MotionHub
---

# MotionHub

**MotionHub** is a curated multi-domain human-motion dataset collection released for training and evaluating generalist motion models. The released version contains motion, language, music, speech, and two-person interaction supervision in a unified MotionHub annotation format.

This Hugging Face dataset card is the public entry point for the processed MotionHub release used by **VersatileMotion (ECCV 2026)**. Every subset listed below has been visually inspected, converted to the repository SMPL-H convention, re-split where needed, and uploaded after data-quality review.

## Highlights

| Scale | Language Supervision | Audio, Music, and Interaction |
|---|---|---|
| **20** released subsets<br>**1.11M** clips<br>**1,528 h** motion<br>**164.98M** frames | **3.31M** text-to-motion prompts<br>**3.31M** motion-to-text references<br>macro / meso / micro caption levels | **5.6K** music-to-dance pairs<br>**44.1K** speech/audio-to-gesture pairs<br>**44.1K** script-to-gesture scripts<br>**23.6K** interaction text-to-motion pairs |

## Task Previews

The previews below are rendered with Three.js from the released SMPL-H motion files. Music and speech examples include the paired source audio where available.

<table>
  <tr>
    <td width="50%">
      <strong>Text-to-motion</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/text_to_motion.mp4" controls loop playsinline width="100%"></video>
    </td>
    <td width="50%">
      <strong>Motion-to-text</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/motion_to_text.mp4" controls loop playsinline width="100%"></video>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <strong>Music-to-dance</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/music_to_dance.mp4" controls loop playsinline width="100%"></video>
    </td>
    <td width="50%">
      <strong>Speech/audio-to-gesture</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/speech_audio_to_gesture.mp4" controls loop playsinline width="100%"></video>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <strong>Script-to-gesture</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/script_to_gesture.mp4" controls loop playsinline width="100%"></video>
    </td>
    <td width="50%">
      <strong>Interaction text-to-motion</strong><br>
      <video src="https://huggingface.co/datasets/ZeyuLing/MotionHub/resolve/main/assets/readme_previews/interaction_text_to_motion.mp4" controls loop playsinline width="100%"></video>
    </td>
  </tr>
</table>

## Quick Start

Download the complete release:

```bash
huggingface-cli download ZeyuLing/MotionHub \
  --repo-type dataset \
  --local-dir MotionHub
```

Download one subset only:

```bash
huggingface-cli download ZeyuLing/MotionHub \
  --repo-type dataset \
  --include "aist/**" "aist/*.json" \
  --local-dir MotionHub
```

Python access:

```python
from huggingface_hub import snapshot_download

root = snapshot_download(
    repo_id="ZeyuLing/MotionHub",
    repo_type="dataset",
    local_dir="MotionHub",
)
```

## Data Format

Each subset follows the same high-level structure:

```text
<subset>/
  train.json
  test.json
  stats.json
  smplh_52/                  # SMPL-H motion NPZ files
  hierarchical_caption/       # macro / meso / micro captions
  ...                         # optional music, audio, speech, or pair metadata
```

The motion files are normalized to the MotionHub SMPL-H convention used in this repository. In particular, `trans` / `transl` stores the body-model translation parameter, and the data should not be re-canonicalized in a viewer before quality inspection.

## Released Subsets

| Family | Dataset | Path | Clips | Hours | Supervision | Cite |
|---|---|---|---:|---:|---|---|
| Single-person text-motion | [AMASS_SUP](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/amass_sup) | `amass_sup` | 7,673 | 24.95 | T2M, M2T | AMASS |
| Single-person text-motion | [CombatMotion](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/CombatMotion_seperate) | `CombatMotion_seperate` | 25,987 | 23.26 | T2M, M2T | CombatMotion |
| Single-person text-motion | [EgoBody](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/EgoBody) | `EgoBody` | 980 | 4.06 | T2M, M2T | EgoBody |
| Single-person text-motion | [Fit3D](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/fit3d) | `fit3d` | 944 | 3.14 | T2M, M2T | Fit3D |
| Single-person text-motion | [GRAB](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/GRAB) | `GRAB` | 1,335 | 3.76 | T2M, M2T | GRAB |
| Single-person text-motion | [Human3.6M](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/human36m) | `human36m` | 925 | 2.98 | T2M, M2T | Human3.6M |
| Single-person text-motion | [HumanML3D-AMASS](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/HumanML3D_AMASS) | `HumanML3D_AMASS` | 29,120 | 54.14 | T2M, M2T | HumanML3D + AMASS |
| Single-person text-motion | [HumanML3D-HumanAct12](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/HumanML3D_HumanACT12) | `HumanML3D_HumanACT12` | 2,382 | 2.05 | T2M, M2T | HumanML3D + HumanAct12 |
| Single-person text-motion | [HumanSC3D](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/humansc3d) | `humansc3d` | 688 | 1.12 | T2M, M2T | HumanSC3D |
| Single-person text-motion | [MotionGV](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/MotionGV) | `MotionGV` | 833,121 | 1,114 | T2M, M2T | MotionMillion / Go to Zero |
| Single-person text-motion | [NTU RGB+D 120](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/nturgbd120) | `nturgbd120` | 106,864 | 71.77 | T2M, M2T | NTU RGB+D 120 |
| Single-person text-motion | [PerMo](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/permo) | `permo` | 6,610 | 8.56 | T2M, M2T | PersonaBooth / PerMo |
| Single-person text-motion | [TRUMANS](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/trumans) | `trumans` | 3,623 | 6.89 | T2M, M2T | TRUMANS |
| Dance and music | [AIST++](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/aist) | `aist` | 1,408 | 5.20 | T2M, M2T, music-to-dance | AIST++ |
| Dance and music | [FineDance](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/finedance) | `finedance` | 4,194 | 13.98 | T2M, M2T, music-to-dance | FineDance |
| Speech and gesture | [BEAT v2.0.0](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/beat_v2.0.0) | `beat_v2.0.0` | 21,603 | 57.09 | T2M, M2T, audio-to-gesture, script-to-gesture | BEAT |
| Speech and gesture | [TED-DB](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/ted_db) | `ted_db` | 22,548 | 72.64 | T2M, M2T, audio-to-gesture, script-to-gesture | TED Gesture |
| Two-person interaction | [Chi3D](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/chi3d) | `chi3d` | 912 | 1.48 | T2M, M2T, interaction T2M | CHI3D |
| Two-person interaction | [Hi4D](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/hi4d) | `hi4d` | 300 | 0.33 | T2M, M2T, interaction T2M | Hi4D |
| Two-person interaction | [InterX](https://huggingface.co/datasets/ZeyuLing/MotionHub/tree/main/interx) | `interx` | 34,161 | 56.25 | T2M, M2T, interaction T2M | InterX |

## Task Coverage

| Task | Supervision source | Count |
|---|---|---:|
| Text-to-motion | hierarchical captions to motion | 3,307,116 prompts |
| Motion-to-text | motion to macro / meso / micro captions | 3,307,116 references |
| Music-to-dance | synchronized music and dance motion | 5,602 pairs |
| Speech/audio-to-gesture | speech audio and gesture motion | 44,134 pairs |
| Script-to-gesture | speech transcript and gesture motion | 44,142 scripts |
| Interaction text-to-motion | two-person captions and paired motions | 23,582 pairs |

## Detailed Inventory

<details>
<summary>Open the full subset statistics table</summary>

| Dataset | Splits | Clips | Motion refs | Frames | Hours | Music refs | T2M prompts | M2T motions / refs | Music pairs | Invalid skipped |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| `CombatMotion_seperate` | train:25,887; test:100 | 25,987 | 25,987 | 2,512,093 | 23.26 | 0 | 77,961 | 25,987 / 77,961 | 0 | 0 |
| `EgoBody` | train:931; test:49 | 980 | 980 | 438,956 | 4.06 | 0 | 2,940 | 980 / 2,940 | 0 | 0 |
| `GRAB` | train:1,268; test:67 | 1,335 | 1,335 | 406,264 | 3.76 | 0 | 4,005 | 1,335 / 4,005 | 0 | 0 |
| `HumanML3D_AMASS` | train:25,160; test:3,960 | 29,120 | 29,120 | 5,846,940 | 54.14 | 0 | 87,360 | 29,120 / 87,360 | 0 | 0 |
| `HumanML3D_HumanACT12` | train:2,040; test:342 | 2,382 | 2,382 | 221,232 | 2.05 | 0 | 7,146 | 2,382 / 7,146 | 0 | 0 |
| `MotionGV` | train:833,121 | 833,121 | 833,121 | 120,306,859 | 1,114 | 0 | 2,499,351 | 833,117 / 2,499,351 | 0 | 0 |
| `aist` | train:1,388; test:20 | 1,408 | 1,408 | 562,091 | 5.20 | 1,408 | 4,224 | 1,408 / 4,224 | 1,408 | 0 |
| `amass_sup` | train:7,373; test:300 | 7,673 | 7,673 | 2,694,691 | 24.95 | 0 | 23,019 | 7,673 / 23,019 | 0 | 0 |
| `beat_v2.0.0` | train:21,234; test:369 | 21,603 | 21,603 | 6,165,861 | 57.09 | 0 | 55,803 | 18,601 / 55,803 | 0 | 0 |
| `chi3d` | train:819; test:93 | 912 | 1,216 | 159,564 | 1.48 | 0 | 2,736 | 912 / 2,736 | 0 | 0 |
| `finedance` | train:4,097; test:97 | 4,194 | 4,194 | 1,509,840 | 13.98 | 4,194 | 12,582 | 4,194 / 12,582 | 4,194 | 43 |
| `fit3d` | train:934; test:10 | 944 | 944 | 338,904 | 3.14 | 0 | 2,832 | 944 / 2,832 | 0 | 0 |
| `hi4d` | train:231; test:69 | 300 | 400 | 35,835 | 0.33 | 0 | 900 | 300 / 900 | 0 | 0 |
| `human36m` | train:915; test:10 | 925 | 925 | 322,172 | 2.98 | 0 | 2,775 | 925 / 2,775 | 0 | 0 |
| `humansc3d` | train:653; test:35 | 688 | 688 | 120,978 | 1.12 | 0 | 2,064 | 688 / 2,064 | 0 | 0 |
| `interx` | train:29,037; test:5,124 | 34,161 | 45,548 | 6,074,619 | 56.25 | 0 | 102,483 | 34,161 / 102,483 | 0 | 0 |
| `nturgbd120` | train:105,904; test:960 | 106,864 | 106,864 | 7,751,049 | 71.77 | 0 | 320,592 | 106,864 / 320,592 | 0 | 0 |
| `permo` | train:6,543; test:67 | 6,610 | 6,610 | 924,726 | 8.56 | 0 | 19,830 | 6,610 / 19,830 | 0 | 0 |
| `ted_db` | train:22,179; test:369 | 22,548 | 22,548 | 7,845,112 | 72.64 | 0 | 67,644 | 22,548 / 67,644 | 0 | 0 |
| `trumans` | train:3,586; test:37 | 3,623 | 3,623 | 743,584 | 6.89 | 0 | 10,869 | 3,623 / 10,869 | 0 | 0 |

</details>

## Quality and Scope Notes

- This release includes only subsets that have passed visual inspection and format review.
- Low-quality or ambiguous subsets from earlier internal processing passes are intentionally excluded from the public release.
- Source datasets retain their own licenses and usage restrictions. Please check and follow the upstream license for every subset you use.
- The statistics above are counted from MotionHub annotations. Frame counts are read from `num_frames` when available, otherwise from duration and FPS.

## Citation

Please cite MotionHub through the VersatileMotion ECCV 2026 paper and also cite every original subset used in your experiment.

### MotionHub / VersatileMotion

```bibtex
@inproceedings{ling2026versatilemotion,
  title={VersatileMotion: A Unified Framework for Motion Synthesis and Comprehension},
  author={Ling, Zeyu and Han, Bo and Li, Shiyang and Cheng, Jikang and Shen, Hongdeng and Zou, Changqing},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2026}
}
```

### Source Datasets

#### AMASS / AMASS_SUP

```bibtex
@conference{AMASS:ICCV:2019,
  title={{AMASS}: Archive of Motion Capture as Surface Shapes},
  author={Mahmood, Naureen and Ghorbani, Nima and Troje, Nikolaus F. and Pons-Moll, Gerard and Black, Michael J.},
  booktitle={International Conference on Computer Vision},
  pages={5442--5451},
  year={2019}
}
```

#### AIST++

```bibtex
@inproceedings{li2021aistpp,
  title={AI Choreographer: Music Conditioned 3D Dance Generation with AIST++},
  author={Li, Ruilong and Yang, Shan and Ross, David A. and Kanazawa, Angjoo},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2021}
}
```

#### BEAT

```bibtex
@inproceedings{liu2022beat,
  title={BEAT: A Large-Scale Semantic and Emotional Multi-Modal Dataset for Conversational Gestures Synthesis},
  author={Liu, Haiyang and Zhu, Zihao and Iwamoto, Naoya and Peng, Yichen and Li, Zhengqing and Zhou, You and Bozkurt, Elif and Zheng, Bo},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2022}
}
```

#### Chi3D

```bibtex
@inproceedings{fieraru2020chi3d,
  title={Three-Dimensional Reconstruction of Human Interactions},
  author={Fieraru, Mihai and Zanfir, Mihai and Oneata, Elisabeta and Popa, Alin-Ionut and Olaru, Vlad and Sminchisescu, Cristian},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2020}
}
```

#### CombatMotion

```bibtex
@misc{liao2024animationgpt,
  title={AnimationGPT: An AIGC Tool for Generating Game Combat Motion Assets},
  author={Liao, Yihao and Fu, Yiyu and Cheng, Ziming and Wang, Jiangfeiyang},
  year={2024},
  howpublished={\url{https://github.com/fyyakaxyy/AnimationGPT}}
}
```

#### EgoBody

```bibtex
@inproceedings{zhang2022egobody,
  title={EgoBody: Human Body Shape and Motion of Interacting People from Head-Mounted Devices},
  author={Zhang, Siwei and Ma, Qianli and Zhang, Yan and Qian, Zhiyin and Kwon, Taein and Pollefeys, Marc and Bogo, Federica and Tang, Siyu},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2022}
}
```

#### FineDance

```bibtex
@inproceedings{li2023finedance,
  title={FineDance: A Fine-grained Choreography Dataset for 3D Full Body Dance Generation},
  author={Li, Ronghui and Zhao, Junfan and Zhang, Yachao and Su, Mingyang and Ren, Zeping and Zhang, Han and Tang, Yansong and Li, Xiu},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2023}
}
```

#### Fit3D

```bibtex
@inproceedings{fieraru2021aifit,
  title={AIFit: Automatic 3D Human-Interpretable Feedback Models for Fitness Training},
  author={Fieraru, Mihai and Zanfir, Mihai and Pirlea, Silviu-Cristian and Olaru, Vlad and Sminchisescu, Cristian},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2021}
}
```

#### GRAB

```bibtex
@inproceedings{taheri2020grab,
  title={{GRAB}: A Dataset of Whole-Body Human Grasping of Objects},
  author={Taheri, Omid and Ghorbani, Nima and Black, Michael J. and Tzionas, Dimitrios},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2020}
}
```

#### Hi4D

```bibtex
@inproceedings{yin2023hi4d,
  title={Hi4D: 4D Instance Segmentation of Close Human Interaction},
  author={Yin, Yifei and Guo, Chen and Kaufmann, Manuel and Zarate, Juan Jose and Song, Jie and Hilliges, Otmar},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2023}
}
```

#### Human3.6M

```bibtex
@article{h36m_pami,
  title={Human3.6M: Large Scale Datasets and Predictive Methods for 3D Human Sensing in Natural Environments},
  author={Ionescu, Catalin and Papava, Dragos and Olaru, Vlad and Sminchisescu, Cristian},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  volume={36},
  number={7},
  pages={1325--1339},
  year={2014}
}
```

#### HumanAct12

```bibtex
@inproceedings{guo2020action2motion,
  title={Action2Motion: Conditioned Generation of 3D Human Motions},
  author={Guo, Chuan and Zuo, Xinxin and Wang, Sen and Zou, Shihao and Sun, Qingyao and Deng, Annan and Gong, Minglun and Cheng, Li},
  booktitle={ACM International Conference on Multimedia},
  pages={2021--2029},
  year={2020}
}
```

#### HumanML3D

```bibtex
@inproceedings{guo2022generating,
  title={Generating Diverse and Natural 3D Human Motions from Text},
  author={Guo, Chuan and Zuo, Xinxin and Wang, Sen and Zou, Shihao and Sun, Qingyao and Deng, Annan and Gong, Minglun and Cheng, Li},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2022}
}
```

#### HumanSC3D

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

#### InterX

```bibtex
@inproceedings{xu2024interx,
  title={Inter-X: Towards Versatile Human-Human Interaction Analysis},
  author={Xu, Liang and Lv, Xintao and Yan, Yichao and Jin, Xin and Wu, Shuwen and Xu, Congsheng and Liu, Yifan and Zhou, Yizhou and Rao, Fengyun and Sheng, Xingdong and Liu, Yunhui and Zeng, Wenjun and Yang, Xiaokang},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2024}
}
```

#### MotionGV / MotionMillion

```bibtex
@article{fan2025go,
  title={Go to Zero: Towards Zero-shot Motion Generation with Million-scale Data},
  author={Fan, Ke and Lu, Shunlin and Dai, Minyue and Yu, Runyi and Xiao, Lixing and Dou, Zhiyang and Dong, Junting and Ma, Lizhuang and Wang, Jingbo},
  journal={arXiv preprint arXiv:2507.07095},
  year={2025}
}
```

#### NTU RGB+D 120

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

#### PerMo / PersonaBooth

```bibtex
@inproceedings{kim2025personabooth,
  title={PersonaBooth: Personalized Text-to-Motion Generation},
  author={Kim, Boeun and Jeong, Hea In and Sung, JungHoon and Cheng, Yihua and Lee, Jeongmin and Chang, Ju Yong and Choi, Sang-Il and Choi, Younggeun and Shin, Saim and Kim, Jungho and Chang, Hyung Jin},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2025}
}
```

#### TED Gesture

```bibtex
@inproceedings{yoon2019ted_gesture,
  title={Robots Learn Social Skills: End-to-End Learning of Co-Speech Gesture Generation for Humanoid Robots},
  author={Yoon, Youngwoo and Ko, Woo-Ri and Jang, Minsu and Lee, Jaeyeon and Kim, Jaehong and Lee, Geehyuk},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  year={2019}
}
```

#### TRUMANS

```bibtex
@inproceedings{jiang2024trumans,
  title={Scaling Up Dynamic Human-Scene Interaction Modeling},
  author={Jiang, Nan and Zhang, Zhiyuan and Li, Hongjie and Ma, Xiaoxuan and Wang, Zan and Chen, Yixin and Liu, Tengyu and Zhu, Yixin and Huang, Siyuan},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2024}
}
```
