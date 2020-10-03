# MICCAI2020

### General questions:
- Release code? When comparing with other works, what if their work implementation is not publicly available?
- Dataset size, how to ensure a robust evaluation when data is small? Limited labled data make both training and evaluating difficult. How to ensure a fair comparison?

### Self-supervised learning B 10:00 AM - 10:30 AM CDT on Monday, 5 October

* [x] User-Guided Domain Adaptation for Rapid Annotation from User Interactions: A Study on Pathological Liver Segmentation - Raju, Ashwin; Ji, Zhanghexuan; Cheng, Chi Tung; Cai, Jinzheng; Huang, Junzhou; Xiao, Jing; Lu, Le; Liao, ChienHung; Harrison, Adam P., University of Texas, Arlington
* [x] SALAD: Self-Supervised Aggregation Learning for Anomaly Detection on X-Rays - Bozorgtabar, Behzad; Mahapatra, Dwarikanath; Vray, Guillaume; Thiran, Jean-Philippe, EPFL
* [x] Scribble-based Domain Adaptation via Deep Co-Segmentation - Dorent, Reuben; Joutard, Samuel; Shapey, Jonathan; Bisdas, Sotirios; Kitchen, Neil; Bradford, Robert ; Saeed, Shakeel; Modat, Marc; Ourselin, Sébastien; Vercauteren, Tom, King's College London
* [x] Source-Relaxed Domain Adaptation for Image Segmentation - Bateson, Mathilde; Kervadec, Hoel; Dolz, Jose; Lombaert, Hervé; Ben Ayed, Ismail, ETS Montréal
* [x] Region-of-interest guided Supervoxel Inpainting for Self-supervision - Kayal, Subhradeep; Chen, Shuai; de Bruijne, Marleen, Erasmus MC
* [x] Harnessing Uncertainty in Domain Adaptation for MRI Prostate Lesion Segmentation - Chiou, Eleni; Giganti, Francesco; Punwani, Shonit; Kokkinos, Iasonas; Panagiotaki,, Eleftheria, University College London

### Semi-supervised Learning C 10:30 AM - 11:00 AM CDT on Monday, 5 October

Deep Q-Network-Driven Catheter Segmentation in 3D US by Hybrid Constrained Semi-Supervised Learning and Dual-UNet - Yang, Hongxu; Shan, Caifeng; Kolen, Alexander F.; de With, P. H. N., Eindhoven University of Technology
Domain Adaptive Relational Reasoning for 3D Multi-Organ Segmentation - Fu, Shuhao; Lu, Yongyi; Wang, Yan; Zhou, Yuyin; Shen, Wei; Fishman, Elliot K.; Yuille, Alan, Johns Hopkins University
Realistic Adversarial Data Augmentation for MR Image Segmentation - Chen, Chen; Qin, Chen; Qiu, Huaqi; Ouyang, Cheng; Wang, Shuo; Chen, Liang; Tarroni, Giacomo; Bai, Wenjia; Rueckert, Daniel, Imperial College London
Learning to Segment Anatomical Structures Accurately from One Exemplar - Lu, Yuhang; Li, Weijian; Zheng, Kang; Wang, Yirui; Harrison, Adam P.; Lin, Chihung; Wang, Song; Xiao, Jing; Lu, Le; Chang-Fu, Kuo; Miao, Shun, University of South Carolina
Uncertainty estimates as data selection criteria to boost omni-supervised learning - Venturini, Lorenzo; Papageorghiou, Aris T.; Noble, J. Alison; Namburete, Ana I.L., University of Oxford
Extreme Consistency: Overcoming Annotation Scarcity and Domain Shifts - Fotedar, Gaurav; Tajbakhsh, Nima; Pundi Ananth, Shilpa; Ding, Xiaowei, Voxelcloud
Spatio-temporal Consistency and Negative LabelTransfer for 3D freehand US Segmentation - Gonzalez Duque, Vanessa; Al Chanti, Dawood; Crouzier, Marion; Nordez, Antoine; Lacourpaille, Lilian; Mateus, Diana, LS2N

### Machine Learning Applications A 11:00 AM - 11:30 AM CDT on Monday, 5 October

* [x] Joint Modeling of Chest Radiographs and Radiology Reports for Pulmonary Edema Assessment - Chauhan, Geeticka; Liao, Ruizhi; Wells III, William M.; Andreas, Jacob; Wang, Xin; Berkowitz, Seth; Horng, Steven; Szolovits, Peter; Golland, Polina, Massachusetts Institute of Technology (MIT)

- This paper aims to classify three labels from chest radiographs and their reports. The input consists of a pair of image and text report. They joint train an imaging encoder and a text encoder (BERT) and in the inference, they only take the trained imaging encoder. Experiments show better performance achieved by joint training than isolated training.
- Q: How to train the unpaired data?

* [x] Domain-specific loss design for unsupervised physical training: A new approach to modeling medical ML solutions - Burwinkel, Hendrik; Matz, Holger; Saur, Stefan; Hauger, Christoph; Evren, Ayse Mine; Hirnschall, Nino; Findl, Oliver; Navab, Nassir; Ahmadi, Seyed-Ahmad, TU München

- Define a loss function based on pysical knowledge. 

* [x] Multiatlas Calibration of Biophysical Brain Tumor Growth Models with Mass Effect - Subramanian, Shashank; Scheufele, Klaudius; Himthani, Naveen; Biros, George, University of Texas at Austin

- When training Models Genesis using L2 loss, would it be helpful to include an additional regularization term? 
- This work simulate tumor on MR images. Can model performance in this simulation be clinically reliable towards real tumors?

* [x] Chest X-ray Report Generation through Fine-Grained Label Learning - Syeda-Mahmood, Tanveer; Wong, Ken C. L.; Gur, Yaniv; Wu, Joy T.; Jadhav, Ashutosh; Kashyap, Satyananda; Karargyris, Alexandros; Pillai, Anup; Sharma, Arjun; Syed, Ali Bin; Boyko, Orest; Moradi, Mehdi, IBM Research

- This work provides a fine-grained labeled ChestXray dataset by NLP learning from reports and automatic report generation. It represents a systematic framework that can potentially be adopted in PE dataset and many other datasets associated with clinical texts. I look forward to see their dataset and implementation of the entire system.

* [x] Spatial Semantic-Preserving Latent Space Learning for Accelerated DWI Diagnostic Report Generation - Gasimova, Aydan; Seegoolam, Gavin; Chen, Liang; Bentley, Paul; Rueckert, Daniel, Imperial College London

- Their presentation video has issue on the website: I can only see half of the talk.

* [x] Peri-Diagnostic Decision Support Through Cost-Efficient Feature Acquisition at Test-Time - Vivar, Gerome; Mullakaeva, Kamilia; Zwergal, Andreas; Navab, Nassir; Ahmadi, Seyed- Ahmad, TUM

- "Peri-diagnostic": Real time computer-aided diagnosis. For example, polyp detection.
- Feature acquisition heatmaps seem very interesting. But I don't fully understand how they analyze this. 
- What is the difference between cost-efficient feature acquisition and active learning?
- Is it possible to use this cost-efficient feature acquisition to image segmentation? 

* [x] A Deep Bayesian Video Analysis Framework: Towards a More Robust Estimation of Ejection Fraction - Kazemi Esfeh, Mohammad Mahdi; Luong, Christina; Behnami, Delaram; Tsang, Teresa ; Abolmaesumi, Purang, University of British Columbia

- Solve a regression problem, making the predicted values more certain.
