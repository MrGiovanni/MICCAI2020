# MICCAI2020

### General questions:
- Release code? When comparing with other works, what if their work implementation is not publicly available?
- Dataset size, how to ensure a robust evaluation when data is small? Limited labled data make both training and evaluating difficult. How to ensure a fair comparison?

### Self-supervised learning A 5:30 AM - 6:00 AM CDT on Monday, 5 October

* [ ] Dual-task Self-supervision for Cross-Modality Domain Adaptation - Xue, Yingying; Feng, Shixiang; Zhang, Ya; Zhang, Xiaoyun; Wang, Yan-Feng, Cooperative Medianet Innovation Center, Shang hai Jiao Tong University
* [ ] Dual-Teacher: Integrating Intra-domain and Inter-domain Teachers for Annotation-efficient Cardiac Segmentation - Li, Kang; Wang, Shujun; Yu, Lequan; Heng, Pheng-Ann, The Chinese University of Hong Kong
* [ ] Test-time Unsupervised Domain Adaptation - Varsavsky, Thomas; Orbes-Arteaga, Mauricio; Sudre, Carole H.; Graham, Mark S.; Nachev, Parashkev; Cardoso, M. Jorge, University College London
* [ ] Self domain adapted network - He, Yufan; Carass, Aaron; Zuo, Lianrui; Dewey, Blake E.; Prince, Jerry L. johns hopkins university
* [ ] Entropy Guided Unsupervised Domain Adaptation for Cross-Center Hip Cartilage Segmentation from MRI - Zeng, Guodong; Schmaranzer, Florian; Lerch, Till D.; Boschung, Adam; Zheng, Guoyan; Burger, Jürgen; Gerber, Kate; Tannast, Moritz; Siebenrock, Klaus; Kim, Young-Jo; Novais, Eduardo N.; Gerber, Nicolas University of Bern



### Semi-supervised learning A 6:00 AM - 6:30 AM CDT on Monday, 5 October

* [ ] Deep Semi-supervised Knowledge Distillation for Overlapping Cervical Cell Instance Segmentation - Zhou, Yanning; Chen, Hao; Lin, Huangjing; Heng, Pheng-Ann, The Chinese University of HongKong
* [ ] DMNet: Difference Minimization Network for Semi-supervised Segmentation in Medical Images - Fang, Kang; Li, Wu-Jun, Nanjing University
* [ ] Double-uncertainty Weighted Method for Semi-supervised Learning - Wang, Yixin; Zhang, Yao; Tian, Jiang; Zhong, Cheng; Shi, Zhongchao; Zhang, Yang; He, Zhiqiang Institute of Computing Technology, Chinese Academy of Sciences; University of Chinese Academy of Sciences
* [ ] Shape-aware Semi-supervised 3D Semantic Segmentation for Medical Images - Li, Shuailin; Zhang, Chuyu; He, Xuming, PLUS Lab, Shanghaitech University
* [ ] Local and Global Structure-aware Entropy Regularized Mean Teacher Model for 3D Left Atrium segmentation - Hang, Wenlong; Feng, Wei; Liang, Shuang; Yu, Lequan; Wang, Qiong; Choi, Kup-Sze; Qin, Jing, Nanjing TECH University
* [ ] Improving dense pixelwise prediction of epithelial density using unsupervised data augmentation for consistency regularization - To, Minh Nguyen Nhat; Sankineni, Sandeep; Xu, Sheng; Turkbey, Baris; Pinto, Peter A.; Moreno, Vanessa; Merino, Maria; Wood, Bradford J.; Kwak, Jin Tae, Sejong University

### Semi-supervised learning B 6:30 AM - 7:00 AM CDT on Monday, 5 October

* [ ] Knowledge-guided Pretext Learning for Utero-placental Interface Detection - Qi, Huan; Collins, Sally; Noble, J. Alison, University of Oxford
* [ ] Self-supervised Depth Estimation to Regularise Semantic Segmentation in Knee Arthroscopy - Liu, Fengbei; Jonmohamadi , Yaqub; Maicas, Gabriel; Pandey, Ajay K.; Carneiro, Gustavo, University of Adelaide
* [ ] Semi-supervised Medical Image Classification with Global Latent Mixing - Gyawali, Prashnna Kumar; Ghimire, Sandesh; Bajracharya, Pradeep; Li, Zhiyuan; Wang, Linwei, Rochester Institute of Technology
* [ ] Self-Loop Uncertainty: A Novel Pseudo-Label for Semi-Supervised Medical Image Segmentation - Li, Yuexiang; Chen, Jiawei; Xie, Xinpeng; Ma, Kai; Zheng, Yefeng, Youtu Lab, Tencent
* [ ] Semi-Supervised Classification of Diagnostic Radiographs with NoTeacher: A Teacher that is not Mean - Unnikrishnan, Balagopal; Nguyen, Cuong Manh; Balaram, Shafa; Foo, Chuan Sheng; Krishnaswamy, Pavitra - Institute for Infocomm Research, A*STAR
* [ ] Predicting Potential Propensity of Adolescents to Drugs via New Semi-Supervised Deep Ordinal Regression Model - Ganjdanesh, Alireza; Ghasedi, Kamran; Zhan, Liang; Cai, Weidong; Huang, Heng, University of Pittsburgh


### Self-supervised learning B 10:00 AM - 10:30 AM CDT on Monday, 5 October

* [x] User-Guided Domain Adaptation for Rapid Annotation from User Interactions: A Study on Pathological Liver Segmentation - Raju, Ashwin; Ji, Zhanghexuan; Cheng, Chi Tung; Cai, Jinzheng; Huang, Junzhou; Xiao, Jing; Lu, Le; Liao, ChienHung; Harrison, Adam P., University of Texas, Arlington

- Liver segmentation is not that challenging task. It would be nicer if this approach can be shown effective on other tasks, such as liver tumor.
- I assume this method is in 2D. Liver is a 3D object; liver in 2D can appear very differently. How to design a loss to constrain liver shape distribution?

* [x] SALAD: Self-Supervised Aggregation Learning for Anomaly Detection on X-Rays - Bozorgtabar, Behzad; Mahapatra, Dwarikanath; Vray, Guillaume; Thiran, Jean-Philippe, EPFL

- Contrastive learning with memory bank in ChestXray imaging. The approach finds the abnormal images by comparing with the normal image feature in the latent space.
- How to define abnormal images in the ChestXray dataset? Healthy and diseased classes? If so, why not directly train a binary classifier? Also, if all 14 diseases in the dataset are considered as abnormal, how to guarantee the model can detect abnormal images with diseases outsider these 14 categories?
- By simply anto-encodering normal images, would abnormal images automatically detected in the inference?

* [x] Scribble-based Domain Adaptation via Deep Co-Segmentation - Dorent, Reuben; Joutard, Samuel; Shapey, Jonathan; Bisdas, Sotirios; Kitchen, Neil; Bradford, Robert ; Saeed, Shakeel; Modat, Marc; Ourselin, Sébastien; Vercauteren, Tom, King's College London

- Assumption 1: Within modality, the voxel with similar spatial location and similar intensity value should belong to the same class.
- Assumption 2: Across modalities, the voxel with similar feature should belong to the same class. (I'm not sure about this assumption: would this inject many noisy?)
- How big is the materix to connect all image voxel within and between images in the dataset?


* [x] Source-Relaxed Domain Adaptation for Image Segmentation - Bateson, Mathilde; Kervadec, Hoel; Dolz, Jose; Lombaert, Hervé; Ben Ayed, Ismail, ETS Montréal

- Domain adaption without using source domain data and target domain labels. In addition to entropy minimisation, this paper introduce a class ratio loss term.
- Why train a class ratio predictor from the source data? The class ratio should be easily accessible from data.
- Entropy minimisation is used in target segmentation where the label is not available. If solely minimizing entropy, the model would predict a blank mask (entropy = 0), therefore, we need an additional loss to ensure class prior. The problem is that class prior does not consider the global structure of the object but only ensure the class ratio. Probably this is the reason why the authors want to train a network to describe class prior.
- I'm not fully understand the conclusion of "entropy regularisation is a useful alternative to supervision in _source_".

* [x] Region-of-interest guided Supervoxel Inpainting for Self-supervision - Kayal, Subhradeep; Chen, Shuai; de Bruijne, Marleen, Erasmus MC

- In-painting diseased regions (using label and super-pixel) is more important than random regions. Would the learned representation be bias on this specific disease, sacrificing the generalizability?
- "Restart U-Net"? Why we need this restart U-Net? If restart U-Net outperforms vanilla U-Net, does it mean the vanilla U-Net has not converged?
- The method requires ground truth, why is it called self-supervised learning? I think it is more like a co-training.

* [x] Harnessing Uncertainty in Domain Adaptation for MRI Prostate Lesion Segmentation - Chiou, Eleni; Giganti, Francesco; Punwani, Shonit; Kokkinos, Iasonas; Panagiotaki,, Eleftheria, University College London (&#9733;)

- Generate high-quality synthetic images as data augmentation for image segmentation task. For example, if there are large number of images and segmentation masks in dataset A, but limited labeled images in dataset B, this method can be used to improve the segmentation accuracy for dataset B.
- https://github.com/elchiou/DA (not available yet)



### Semi-supervised Learning C 10:30 AM - 11:00 AM CDT on Monday, 5 October

* [ ] Deep Q-Network-Driven Catheter Segmentation in 3D US by Hybrid Constrained Semi-Supervised Learning and Dual-UNet - Yang, Hongxu; Shan, Caifeng; Kolen, Alexander F.; de With, P. H. N., Eindhoven University of Technology
* [ ] Domain Adaptive Relational Reasoning for 3D Multi-Organ Segmentation - Fu, Shuhao; Lu, Yongyi; Wang, Yan; Zhou, Yuyin; Shen, Wei; Fishman, Elliot K.; Yuille, Alan, Johns Hopkins University
* [ ] Realistic Adversarial Data Augmentation for MR Image Segmentation - Chen, Chen; Qin, Chen; Qiu, Huaqi; Ouyang, Cheng; Wang, Shuo; Chen, Liang; Tarroni, Giacomo; Bai, Wenjia; Rueckert, Daniel, Imperial College London
* [ ] Learning to Segment Anatomical Structures Accurately from One Exemplar - Lu, Yuhang; Li, Weijian; Zheng, Kang; Wang, Yirui; Harrison, Adam P.; Lin, Chihung; Wang, Song; Xiao, Jing; Lu, Le; Chang-Fu, Kuo; Miao, Shun, University of South Carolina
* [ ] Uncertainty estimates as data selection criteria to boost omni-supervised learning - Venturini, Lorenzo; Papageorghiou, Aris T.; Noble, J. Alison; Namburete, Ana I.L., University of Oxford
* [ ] Extreme Consistency: Overcoming Annotation Scarcity and Domain Shifts - Fotedar, Gaurav; Tajbakhsh, Nima; Pundi Ananth, Shilpa; Ding, Xiaowei, Voxelcloud
* [ ] Spatio-temporal Consistency and Negative LabelTransfer for 3D freehand US Segmentation - Gonzalez Duque, Vanessa; Al Chanti, Dawood; Crouzier, Marion; Nordez, Antoine; Lacourpaille, Lilian; Mateus, Diana, LS2N

### Machine Learning Applications A 11:00 AM - 11:30 AM CDT on Monday, 5 October

* [x] Joint Modeling of Chest Radiographs and Radiology Reports for Pulmonary Edema Assessment - Chauhan, Geeticka; Liao, Ruizhi; Wells III, William M.; Andreas, Jacob; Wang, Xin; Berkowitz, Seth; Horng, Steven; Szolovits, Peter; Golland, Polina, Massachusetts Institute of Technology (MIT)

- This paper aims to classify three labels from chest radiographs and their reports. The input consists of a pair of image and text report. They joint train an imaging encoder and a text encoder (BERT) and in the inference, they only take the trained imaging encoder. Experiments show better performance achieved by joint training than isolated training.
- Q: How to train the unpaired data?

* [x] Domain-specific loss design for unsupervised physical training: A new approach to modeling medical ML solutions - Burwinkel, Hendrik; Matz, Holger; Saur, Stefan; Hauger, Christoph; Evren, Ayse Mine; Hirnschall, Nino; Findl, Oliver; Navab, Nassir; Ahmadi, Seyed-Ahmad, TU München

- Define a loss function based on pysical knowledge. 

* [x] Multiatlas Calibration of Biophysical Brain Tumor Growth Models with Mass Effect - Subramanian, Shashank; Scheufele, Klaudius; Himthani, Naveen; Biros, George, University of Texas at Austin

- When training Models Genesis using L2 loss, would it be helpful to include an additional regularization term? 
- This work simulate tumor on MR images. Can model performance in this simulation be clinically reliable towards real tumors?

* [x] Chest X-ray Report Generation through Fine-Grained Label Learning - Syeda-Mahmood, Tanveer; Wong, Ken C. L.; Gur, Yaniv; Wu, Joy T.; Jadhav, Ashutosh; Kashyap, Satyananda; Karargyris, Alexandros; Pillai, Anup; Sharma, Arjun; Syed, Ali Bin; Boyko, Orest; Moradi, Mehdi, IBM Research (&#9733;)

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
