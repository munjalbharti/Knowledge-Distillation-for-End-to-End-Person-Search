# Knowledge-Distillation-for-End-to-End-Person-Search

This is the project page for our work at BMVC 2019. 

Paper Link: https://arxiv.org/abs/1909.01058

If you are referring this work please cite:

@inproceedings{munjal2019knowledge,
  title={Knowledge Distillation for End-to-End Person Search},
  author={Munjal, Bharti and Amin, Sikandar and Galasso, Fabio},
  booktitle={The British Machine Vision Conference (BMVC)},
  year={2019}
}

## Abstract
We introduce knowledge distillation for end-to-end person search. End-to-End methods are the current state-of-the-art for person search that solve both detection and re-identification jointly. These approaches for joint optimization show their largest drop in performance due to a sub-optimal detector.
We propose two distinct approaches for extra supervision of end-to-end person search methods in a teacher-student setting. The first is adopted from state-of-the-art knowledge distillation in object detection. We employ this to supervise the detector of our person search model at various levels using a specialized detector. The second approach is new, simple and yet considerably more effective. This distills knowledge from a teacher re-identification technique via a pre-computed look-up table of ID features. It relaxes the learning of identification features and allows the student to focus on the detection task. This procedure not only helps fixing the sub-optimal detector training in the joint optimization and simultaneously improving the person search, but also closes the performance gap between the teacher and the student for model compression in this case. Overall, we demonstrate significant improvements for two recent state-of-the-art methods using our proposed knowledge distillation approach on two benchmark datasets. Moreover, on the model compression task our approach brings the performance of smaller models on par with the larger models.

## Results on CUHK-SYSU [2] using Resnet50

| Method        | Person Search mAP           | Person Search top-1  |  Detection mAP |  Detection Recall | 
|  -------------            |:-------------:| -----: | -----: | -----:|
| Detect + OIM                 | 78.0          |   77.9 | 75.2| 82.7|
| QEEPS [1]                  | 84.4          |   84.4 | -| -| 
| Detect + OIM with QEEPS Teacher (Our Proposed)                    | 83.8          |   84.2  | 81.7| 86.8|

## Results on CUHK-SYSU [2] using Resnet18  
| Method        | Person Search mAP           | Person Search top-1  | Detection mAP |  Detection Recall | 
|  -------------            |:-------------:| -----: | -----: | -----:|
| Detect + OIM (ours)                   | 69.1          |   68.0 | 74.2| 81.6|
| Detect + OIM with QEEPS Teacher (Our Proposed)                   | 82.4         |   83.0  | 80.8| 86.0|


[1] B. Munjal, S. Amin, F. Tombari, F. Galasso. Query-guided End-to-End Person Search. In The IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2019

[2] T. Xiao, S. Li, B. Wang, L. Lin, and X. Wang. Joint detection and identification feature learning for person search. In The IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017.

