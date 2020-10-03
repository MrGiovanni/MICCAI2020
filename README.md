# MICCAI2020

### General questions:
- Release code? When comparing with other works, what if their work implementation is not publicly available?
- Dataset size, how to ensure a robust evaluation when data is small? Limited labled data make both training and evaluating difficult. How to ensure a fair comparison?

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
