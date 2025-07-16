# Few-Shot Learning-Based Glaucoma Detection System


📌 Overview

This project proposes a data-efficient and interpretable pipeline for glaucoma detection using few-shot segmentation and prototype-based classification. The framework mimics the clinical workflow by segmenting key anatomical biomarkers — the optic disc (OD), optic cup (OC), and retinal blood vessels — and combines them with raw fundus images to classify as Normal or Glaucoma. The system leverages the strengths of Prototypical Networks, attention mechanisms, and ConvNeXt-based backbones for robust performance in low-resource settings.


🧰 Tech Stack

Python

PyTorch – Deep learning framework

NumPy, OpenCV, PIL – Preprocessing

Matplotlib, Seaborn – Visualization

scikit-learn – Metrics

LaTeX – Report generation

Overleaf – Paper writing


📂 Dataset Used

REFUGE, ORIGA – For optic disc & cup segmentation

FIVES, RBVS – For blood vessel segmentation

LAG, AIROGS – For classification and evaluation


🧠 Methodology

1. Few-Shot Segmentation
   
Two separate Prototypical Networks:

OC/OD segmentation using masked average pooling.

Blood vessel segmentation using Proto-UNet.

Trained with <10 annotated support images per class.

2. Mask-Based Fusion
   
Segmentation outputs are overlaid and stacked with raw fundus images to form 3-channel composite inputs.

3. Classification
   
A ConvNeXt-based classifier with attention receives these composite inputs.

Trained in a Prototypical Network-style episodic learning setup.


📊 Evaluation Metrics

Accuracy, ROC AUC, Precision, Recall, F1-Score, Sensitivity, Specificity

Dice Coefficient and IoU for segmentation


Ablation Study: Evaluates performance across input configurations:

A1: Image + Masks (Proposed)

A2: Masks Only

A3: Image Only

📌 Results Summary
Input  Config   	   Accuracy 	ROC AUC	  F1-Score
A1    (Proposed)	    0.7150	  0.7705	  0.7150
A2    (Masks Only)	  0.6030	  0.6496	  0.6030
A3    (Image Only)	  0.5780    0.5938    0.5779


📜 Conclusion

This work presents a lightweight, interpretable, and data-efficient glaucoma detection framework capable of operating effectively under limited supervision. The integration of anatomical priors — derived via few-shot segmentation of optic disc, cup, and vessels — with raw image data significantly enhances classification accuracy and generalization. The use of Prototypical Networks provides robustness against data scarcity, while the attention-guided ConvNeXt classifier ensures focused and explainable decision-making. The ablation studies confirm that combining both structural and visual modalities yields superior performance over using them in isolation. The system is highly applicable to real-world screening scenarios, especially in low-resource clinical environments.
