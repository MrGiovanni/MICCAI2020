# MICCAI2020

### Questions to panel:
- Q: Thank you all for the wonderful presentations. Have you released code to reproduce the success in the paper? When comparing with other works, what if their work implementation is not publicly available? How would you ensure a fair comparison in the study?
- Q: I would like to ask the whole panel to first remind us of the dataset size that you used in the paper. Limited labeled data make both training and evaluating difficult. Many of you proposed wonderful methods to overcome the training challenges using limited data, but how do you ensure a reliable evaluation of the method using such a small labeled data in target tasks? Do you think we still need to collect a large labeled dataset for the evaluation of the methods?

### General comments:
- I think supervised domain adaption (SDA) makes more sense than unsupervised domain adaptation (UDA). To evaluate the UDA, we have to collect a large amount of labeled data for the target task anyhow. If the annotation in the target domain cannot be avoided, why not train models in a supervised manner on these annotations? In this case, one may argue that we do not have a test set for the target task. It is true, but we all agree that supervised models are supposed to outperform UDA models in general, so we do not need an additional test set to approve this assumption. Instead of using the annotated data in the target task for evaluation purposes, I would directly employ it as an available annotation for supervised training.

### Highlights:
- MONAI is a good platform for medical imaging that I should use.
- NVIDIA releases powerful models for COVID-19 segmentation [link](https://ngc.nvidia.com/catalog/models?orderBy=modifiedDESC&pageNumber=0&query=covid&quickFilter=models&filters=)
- Application -> model -> annotation -> data
- ML Code Completeness Checklist [blog](https://medium.com/paperswithcode/ml-code-completeness-checklist-e9127b168501) | [github](https://github.com/paperswithcode/releasing-research-code) 
- MICCAI Reproducibility Checklist [link](https://github.com/JunMa11/MICCAI-Reproducibility-Checklist)
- Segmentation uncertainty by Jun Ma (I cannot find the paper, but its title is "Estimating Segmentation Uncertainties Like Radiologists")
- Segmentation uncertainty and error estimation in medical imaging. [slides](https://labels.tue-image.nl/wp-content/uploads/2018/09/Keynote-Joskoxicz.pdf)
- Bias field transformation for MRI imaging (`Chen et al. MICCAI 2020`). Adversarial noise may not exist in the real world medical imaging, therefore cannot contribute to model generalizability much.
- Learn from an examplar X-ray image - how to find examplar? (`Lu et al. MICCAI 2020`)
- A reading list for self/semi-supervised learning in MICCAI 2020 https://zhuanlan.zhihu.com/p/266299852

## Something I didn't know before
- Common paradigm of domain adaption / semi-supervised learning. I found the basic idea was clearly presented in (`Minh To et al. MICCAI 2020`). Consider if Models Genesis could help this paradigm (their framework)?
- Many consistency loss: edge consistency, segmentation consistency (different data-augmentation). The fundamental observation of consistency loss is very similar to our AIFT paper (`Zhou et al. CVPR 2017`). Based upon this, we can devise new active learning criteria for image segmentation.
- Unsupervised domain adaption consists of image appearance adaptation and feature alignment.
- Auxiliary self-supervised learning (alternative term for multi-task self-supervised learning or A regularizing B during training )
- Two interesting concepts: epistemic (model) uncertainty and aleatoric (data) uncertainty (`Venturini et al. MICCAI 2020`)

## Paper reading:

* [x] Difficulty-aware Meta-learning for Rare Disease Diagnosis

    - Speaker: Xiaomeng Li
    - Train a model on common diseases and test it on rare diseases. How many predictions does the model output? Equal to # of common diseases or equal to # of (common and rare diseases)?
    - Not sure why use meta-learning instead of transfer learning. What is the fundamental benefits?
    - Difficult-aware: use difficult as weight of loss, larger weights for difficult and smaller weights for easy tasks. But normal backpropagation can automatically do this: difficult batch have higher loss (contribute more on weight updates) and easy batches have lower loss (contribute less). What is the reason to enhance this difference?

* [x] Cascaded Robust Learning at Imperfect Labels for Chest X-ray Segmentation

    - Speaker: Xue Cheng

## Area chair duty: Prepare questions for individual paper in sessions

### Self-supervised learning A 5:30 AM - 6:00 AM CDT on Monday, 5 October

* [x] Dual-task Self-supervision for Cross-Modality Domain Adaptation
  - Speaker: Yingying Xue
  - Q: Segmentation ground truth in the edge region of an object, especially in medical images, is usually wrong due to human error. Even two human experts cannot guarantee edge consistency during the annotation process. Do you think it is too restricted, or why do you think it is necessary to train models with this edge consistency loss?
  - Dual-task: segmentation and edge detection tasks in the source domain.
  - Note: In the target domain, edge consistency loss is applied.


* [x] Dual-Teacher: Integrating Intra-domain and Inter-domain Teachers for Annotation-efficient Cardiac Segmentation
  - Speaker: Kang Li
  - Q: Instead of two teachers helping one student, how about two teachers train jointly? The key question is: why do we need a student network as a bridge?
  - Note: Utilize labeled source domain data (generating synthetic data by CycleGAN), labeled target domain data, and unlabeled target domain data (consistency loss).
  - Note: This consistency loss is very similar to Extreme Consistency (Fotedar et al. MICCAI 2020).
  - Note: Since the labeled source domain should also fully annotated for segmenting the same object as the target domain, can I understand this work uses way more annotations than other baselines? For example, I have dataset A (source domain) consisting of 1,000 labeled images for lung segmentation, another dataset B (target domain) with 10 labeled images for lung segmentation. This method adapts labels from A to B so as to, somehow, merge two datasets. I think it is interesting to have a performance reference, in which the model is supervised trained on both datasets A and B, to demonstrate this domain adaptation benefits more than simply merging two datasets and training.

* [x] Test-time Unsupervised Domain Adaptation
  - Speaker: Thomas Varsavsky
  - Q: Could you explain more about the conclusion: "a UDA model will perform better on the unlabeled scans it is trained on than those that are completely unseen." 
  - Note: Supervised loss + adversarial loss (bringing two domains closer in the feature space) + paired consistency
   

* [x] Self domain adapted network
  - Speaker: Yufan He
  - Note: To thoroughly validate the performance of domain adaptation, large annotated data is needed. With this in mind, why not we train a supervised model directly on this big labeled data?

* [x] Entropy Guided Unsupervised Domain Adaptation for Cross-Center Hip Cartilage Segmentation from MRI
  - Speaker: Guodong Zeng
  - Q: What is the intuition behind entropy alignment? The purpose explained in the paper is to let the model focus more on uncertain regions, but how to relate this purpose with the proposed methodology (align entropy maps between source and target domains).
  - Note: Unsupervised domain adaption: image appearance adaptation (the one in the `Fixed-Point GAN journal version`) and feature alignment (learning domain invariant feature).
  - Note: There are two discriminators: one for distinguishing feature maps between two domains, the other for distinguishing entropy maps between two domains (this is new). 



### Semi-supervised learning A 6:00 AM - 6:30 AM CDT on Monday, 5 October

* [x] Deep Semi-supervised Knowledge Distillation for Overlapping Cervical Cell Instance Segmentation
  - Speaker: Yanning Zhou
  - Q: How is your method different from other existing teacher-student network-based knowledge distillation?
  - Semi-supervised learning: consistency regularization, pseudo-labeling, entropy-based methods.

* [x] DMNet: Difference Minimization Network for Semi-supervised Segmentation in Medical Images
  - Speaker: Kang Fang
  - Q: Why the existing co-training based semi-supervised methods cannot be trained end-to-end?
  - Q: Could you discuss the difference between difference minimization and consistency minimization, which has been widely used in semi-supervised learning?

* [x] Double-uncertainty Weighted Method for Semi-supervised Learning
  - Speaker: Yixin Wang
  - Q: What is the advantage and disadvantage of measuring feature uncertainty compared with segmentation uncertainty?
  - Q: Could you discuss the difference between computing feature uncertainty and feature consistency in teacher-student networks?
  - Segmentation uncertainty: entropy of each predicted pixel class.
  - Note: Why do we need a teacher-student network here?
  - Note: [_new_] Feature uncertainty. I do not follow the intuition of measuring feature uncertainty illustrated in the presentation. To compare the consistency of activated regions in the feature maps, why not directly calculate the distance between each feature map in teacher and student networks?

* [x] Shape-aware Semi-supervised 3D Semantic Segmentation for Medical Images
  - Speaker: Chuyu Zhang
  - Q: When computing the adversarial loss to ensure the shape similarity, why do you use the SDM rather than the mask?
  - Note: The presentation of this paper provides a great overview of existing semi-supervised learning approaches. (&#9733;)
  - Note: Their code is publicly available: https://github.com/kleinzcy/SASSnet

* [x] Local and Global Structure-aware Entropy Regularized Mean Teacher Model for 3D Left Atrium segmentation
  - Speaker: Wenlong Hang
  - Q: By entropy minimization principle, the network is forced to make more confident predictions on the object's boundary. However, in practice, even for human experts, it is usually ambiguous to annotated pixels on the object boundary. Therefore, most of the ground truth of the object boundary may not be perfectly correct. I would like to ask your opinion about the entropy minimization principle when facing this issue? 
  - Q: What is the intuition behind local structure consistency? Why should the local structure be consistent among sub-volumes?

* [x] Improving dense pixelwise prediction of epithelial density using unsupervised data augmentation for consistency regularization
  - Speaker: Nguyen Nhat Minh To
  - Q: In your experiment, do the labeled and unlabeled images belong to the same dataset? What if the labeled and unlabeled images come from different domains?
  - Note: This semi-supervised learning paradigm seems very popular in this MICCAI. I can probably use this paradigm to demonstrate Models Genesis improve domain adaptation / semi-supervised learning.


### Self-supervised learning B 10:00 AM - 10:30 AM CDT on Monday, 5 October

* [x] User-Guided Domain Adaptation for Rapid Annotation from User Interactions: A Study on Pathological Liver Segmentation
  - Speaker: Ashwin Raju
  - Q: Have you evaluated this approach on smaller objects, such as liver tumor segmentation?
  - Note: Liver segmentation is not a challenging task. It would be nicer if this approach can be effective on other tasks, such as segmenting liver tumors.
  - Note: I assume this method is in 2D. The liver is a 3D object; in a 2D view, it can appear very differently. How to design a loss to constrain liver shape distribution?

* [x] SALAD: Self-Supervised Aggregation Learning for Anomaly Detection on X-Rays
  - Speaker: Behzad Bozorgtabar
  - Q: ChestXray dataset has 14 labeled diseases. Would this anomaly detection model find any diseases outside these 14 categories?
  - Note: Contrastive learning with memory bank in ChestXray imaging. The approach finds the abnormal images by comparing it with the normal image feature in the latent space.
  - Note: How to define abnormal images in the ChestXray dataset? Healthy and diseased classes? If so, why not directly train a binary classifier? If all 14 diseases in the dataset are considered abnormal, how to guarantee the model can detect abnormal images with diseases outside these 14 categories?
  - Note: By simply auto-encoding normal images, would abnormal images automatically detected in the inference?

* [x] Scribble-based Domain Adaptation via Deep Co-Segmentation
  - Speaker: Reuben Dorent
  - Q: How much memory is needed to compute a matrix that records voxels' connection within and among images in the dataset?
  - Q: You assume that across different modalities, the voxel with similar features should share with the same label. Would this assumption inject many noises?
  - Assumption 1: Within modality, the voxel with similar spatial location and similar intensity value should belong to the same class.
  - Assumption 2: Across modalities, the voxel with similar features should belong to the same class. (I'm not sure about this assumption: would this inject many noisy?)
   


* [x] Source-Relaxed Domain Adaptation for Image Segmentation
  - Speaker: Mathilde Bateson
  - Q: Could you please elaborate more about the conclusion: "entropy regularisation is a useful alternative to supervision in _source_". Why is it in the source domain?
  - Note: Domain adaption without using source domain data and target domain labels. In addition to entropy minimization, this paper introduces a class ratio loss term.
  - Note: Why train a class ratio predictor from the source data? The class ratio should be easily accessible from data.
  - Note: Entropy minimization is used in target segmentation where the label is not available. If solely minimizing entropy, the model would predict a blank mask (entropy = 0); therefore, we need an additional loss to ensure class prior. The problem is that class prior does not consider the object's global structure but only ensures the class ratio. Probably this is the reason why the authors want to train a network to describe class prior.
  - Note: I do not fully understand the conclusion of "entropy regularisation is a useful alternative to supervision in _source_".

* [x] Region-of-interest guided Supervoxel Inpainting for Self-supervision
  - Speaker: Subhradeep Kayal
  - Q: If restart U-Net outperforms vanilla U-Net, does it mean the vanilla U-Net has not converged?
  - Note: In-painting diseased regions (using label and super-pixel) is more important than random regions. Would the learned representation be bias on this specific disease, sacrificing the generalizability?
  - Note: "Restart U-Net"? Why we need this restart U-Net? If restart U-Net outperforms vanilla U-Net, does it mean the vanilla U-Net has not converged?
  - Note: The method requires ground truth; why is it called self-supervised learning? I think it is more like a co-training.

* [x] Harnessing Uncertainty in Domain Adaptation for MRI Prostate Lesion Segmentation 
  - Speaker: Eleni Chiou
  - Note: Generate high-quality synthetic images as data augmentation for image segmentation tasks. For example, if there are a large number of images and segmentation masks in dataset A, but limited labeled images in dataset B, this method can be used to improve the segmentation accuracy for dataset B. (&#9733;)
  - Code: https://github.com/elchiou/DA (not available yet)



### Semi-supervised Learning C 10:30 AM - 11:00 AM CDT on Monday, 5 October

* [x] Deep Q-Network-Driven Catheter Segmentation in 3D US by Hybrid Constrained Semi-Supervised Learning and Dual-UNet
  - Speaker: Hongxu Yang
  - Q: What is the objective function (reward) in the deep Q network?

* [x] Domain Adaptive Relational Reasoning for 3D Multi-Organ Segmentation
  - Speaker: Shuhao Fu
  - Note: Auxiliary self-supervised learning tasks with supervised learning.
   Since domain adaption performance is not higher than supervised learning (upper bound), in practice, to achieve acceptable performance, we still recommend collecting labels for different domains.

* [x] Realistic Adversarial Data Augmentation for MR Image Segmentation (&#9733;)
  - Speaker: Chen Chen
  - Q: Why the bias field is specifically designed for MR images? Would it be useful for CT images?
  - Note: Traditional data augmentation includes affine&elastic transformation and photometric transformation. Advanced data augmentation covers data mixing, generative network-based, and adversarial data augmentation.
  - Note: Adversarial noise may not exist in the real world medical imaging, therefore cannot contribute to model generalizability much. This work proposes a realistic adversarial augmentation, designed explicitly for MR imaging.
  - Note: How to evaluate model generalizability?
  - Note: I love the bias field idea! Compare this with non-linear transformation. (https://github.com/airlab-unibas/airlab; https://github.com/fepegar/torchio)

* [x] Learning to Segment Anatomical Structures Accurately from One Exemplar (&#9733;)
  - Speaker: Yuhang Lu
  - Q: How to find the examplar image from a dataset? Have you investigated any performance difference if you choose different images as examplar?
  - Note: Use feature space to find the sample with lowest distance with all other images.

* [x] Uncertainty estimates as data selection criteria to boost omni-supervised learning (&#9733;)
  - Speaker: Lorenzo Venturini
  - Q: Could you please discuss the difference between Omni-supervised learning in this work and active learning in image segmentation?
  - Note: Two interesting concepts: epistemic (model) uncertainty and aleatoric (data) uncertainty 

* [x] Extreme Consistency: Overcoming Annotation Scarcity and Domain Shifts
  - Speaker: Gaurav Fotedar
  - Q: Is it possible that the extreme augmentation, for example image mixing, makes the object disappear, making the segmentation task infeasible?
  - Note: Consistency loss between teacher and student networks
   

* [x] Spatio-temporal Consistency and Negative LabelTransfer for 3D freehand US Segmentation
  - Speaker: Vanessa Gonzalez Duque
  - Q: How to distinguish the images without annotation and without object (all background)?
  - Note: Handle missing labels of slices in 3D volume.
  - Note: Auxiliary reconstruction with segmentation task.
    

### Machine Learning Applications A 11:00 AM - 11:30 AM CDT on Monday, 5 October

* [x] Joint Modeling of Chest Radiographs and Radiology Reports for Pulmonary Edema Assessment
    - Spearker: Geeticka Chauhan
    - Q: How to train unpaired data?
    - Note: This paper aims to classify three labels from chest radiographs and their reports. The input consists of a pair of image and text report. They joint train an imaging encoder and a text encoder (BERT), and in the inference, they only take the trained imaging encoder. Experiments show better performance achieved by joint training than isolated training.


* [x] Domain-specific loss design for unsupervised physical training: A new approach to modeling medical ML solutions - Burwinkel, Hendrik; Matz, Holger; Saur, Stefan; Hauger, Christoph; Evren, Ayse Mine; Hirnschall, Nino; Findl, Oliver; Navab, Nassir; Ahmadi, Seyed-Ahmad, TU München

    - Note: Define a loss function based on physical knowledge. 

* [x] Multiatlas Calibration of Biophysical Brain Tumor Growth Models with Mass Effect

    - Q: This work simulate tumor on MR images. Can model performance in this simulation be clinically reliable towards real tumors?
    - Note: When training Models Genesis using L2 loss, would it be helpful to include an additional regularization term? 
     

* [x] Chest X-ray Report Generation through Fine-Grained Label Learning (&#9733;)

    - Note: This work provides a fine-grained labeled ChestXray dataset by NLP learning from reports and automatic report generation. It represents a systematic framework that can potentially be adopted in the PE dataset and many other datasets associated with clinical texts. I look forward to seeing their dataset and implementation of the entire system.

* [x] Spatial Semantic-Preserving Latent Space Learning for Accelerated DWI Diagnostic Report Generation

* [x] Peri-Diagnostic Decision Support Through Cost-Efficient Feature Acquisition at Test-Time

    - Q: What is the difference between cost-efficient feature acquisition and active learning?
    - Q: Is it possible to use this cost-efficient feature acquisition for image segmentation? 
    - "Peri-diagnostic": Real-time computer-aided diagnosis. For example, polyp detection.
    - Note: Feature acquisition heatmaps seem very interesting. But I don't fully understand how they analyze this. 
 
 

* [x] A Deep Bayesian Video Analysis Framework: Towards a More Robust Estimation of Ejection Fraction

    - Note: Solve a regression problem, making the predicted values more certain.
