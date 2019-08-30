# OCR调研
OCR目前有三大任务，分别为文本识别，文本检测以及端到端End2End识别，三个任务的分布情况如下图。

![avatar](images/overall_pi_chart.png)

近几年OCR任务的解决方案主要围绕深度学习展开，如下图论文数量变化。
![avatar](images/overall_histogram.png)

## 文本检测
* 论文根据发布时间排列
* IC为ICDAR会议
* Score是文本定位任务的F1-Score
- (L) 代表分数 [leader-board](http://rrc.cvc.uab.es/)
- (L) 目的是区分报道的分数和实际分数的不同
* `*CODE` 指提供源码，  `CODE(M)` 指提供训练好的模型  

![avatar](images/detection_ic13_results.png)
![avatar](images/detection_ic15_results.png)

*Conf.* | *Date* | *Title* | *IC13* | *IC15* | *Resources* |
:---: | :---: |:--- | :---: | :---: | :---: |
'14-ECCV	| 14/10/07	| [Robust Scene Text Detection with Convolution Neural Network Induced MSER Trees](	http://www.whuang.org/papers/whuang2014_eccv.pdf) |
15-CVPR	| 15/06/01	| [Symmetry-based text line detection in natural scenes](https://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Zhang_Symmetry-Based_Text_Line_2015_CVPR_paper.pdf) | [0.8043](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=2197) | | [`PRJ`](http://mclab.eic.hust.edu.cn/~xbai/text/symmetry/SymmetryTextLineDetection.html) <br> [`CODE`](https://github.com/stupidZZ/Symmetry_Text_Line_Detection) |  
'16-TIP	| 15/10/12 | [Text-Attentional Convolutional Neural Networks for Scene Text Detection](https://arxiv.org/pdf/1510.03283.pdf) |	[0.8165](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=7187)	| 
'15-ICCV	| 15/12/13	| [Text Flow : A Unified Text Detection System in Natural Scene Images](https://pdfs.semanticscholar.org/11a0/8ced22775a217ba78c566528ed44ea98e3e3.pdf)	|0.8025 | 
'16-arXiv	| 16/03/31	| [Accurate Text Localization in Natural Image with Cascaded Convolutional TextNetwork](https://arxiv.org/pdf/1603.09423.pdf)	| 0.86	| |
'16-CVPR	| 16/04/14	| [Multi-Oriented Text Detection with Fully Convolutional Networks](https://arxiv.org/pdf/1604.04018.pdf) | 0.83 | 0.54 | [`*TORCH(M)`](https://github.com/stupidZZ/FCN_Text)
'16-CVPR	| 16/04/22	| [Synthetic Data for Text Localisation in Natural Images](http://www.robots.ox.ac.uk/~ankush/textloc.pdf)	| 0.847 <br> (L)[0.8359](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=3820) | | [`CODE`](https://github.com/ankush-me/SynthText) <br> [`DB`](http://www.robots.ox.ac.uk/~vgg/data/scenetext/)
'16-arXiv	| 16/06/29	| [Scene Text Detection Via Holistic， Multi-Channel Prediction](https://arxiv.org/pdf/1606.09002.pdf)	|0.8433	| 0.6477 | 
'16-ECCV	| 16/09/12	| [Detecting Text in Natural Image with Connectionist Text Proposal Network](https://arxiv.org/pdf/1609.03605.pdf) |	[0.8215](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=13931)	| [0.6085](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=13930) | [`*CAFFE(M)`](https://github.com/tianzhi0549/CTPN) <br> [`CAFFE`](https://github.com/qingswu/CTPN) <br> [`TF(M)`](https://github.com/eragonruan/text-detection-ctpn) <br> [`TF`](https://github.com/Li-Ming-Fan/OCR-DETECTION-CTPN) <br> [`DEMO`](http://textdet.com/) <br> [`BLOG(CH)`](http://slade-ruan.me/2017/10/22/text-detection-ctpn/)
'17-AAAI	| 16/11/21	|[TextBoxes: A fast text detector with a single deep neural network](https://arxiv.org/pdf/1611.06779.pdf) |	0.85 <br> (L)[0.8767](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=21928) | | [`*CAFFE(M)`](https://github.com/MhLiao/TextBoxes) <br> [`TF`](https://github.com/shinjayne/shinTB) <br> [`BLOG(KR)`](http://jaynewho.com/post/6)
'18-TM	| 17/03/03	| [Arbitrary-Oriented Scene Text Detection via Rotation Proposals](https://arxiv.org/pdf/1703.01086.pdf)	|	[0.9125](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=15904)	| [0.8020](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=17393)	| [`*CAFFE`](https://github.com/mjq11302010044/RRPN)
'17-CVPR	| 17/03/04	| [Deep Matching Prior Network: Toward Tighter Multi-oriented Text Detection](https://arxiv.org/pdf/1703.01425.pdf) | | [0.7064](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=13007)
'17-CVPR	| 17/03/19	| [Detecting Oriented Text in Natural Images by Linking Segments](https://arxiv.org/pdf/1703.06520.pdf)	|	0.853	| 0.75	<br> (L)[0.7636](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=29245)| [`*TF(M)`](https://github.com/bgshih/seglink) <br> [`TF(M)`](https://github.com/dengdan/seglink) <br> [`SLIDE`](http://mclab.eic.hust.edu.cn/~xbai/SpotlightPPT/TextDetection-seglink-spotlight-CVPR17.pdf) <br> [`VIDEO`](https://www.youtube.com/watch?v=w0vZWUi-m0c) |
'17-arXiv	| 17/03/24 |	[Deep Direct Regression for Multi-Oriented Scene Text Detection](https://arxiv.org/pdf/1703.08289.pdf)	| 0.86 |  0.81	| 
'17-arXiv	| 17/04/03	| [Cascaded Segmentation-Detection Networks for Word-Level Text Spotting](https://arxiv.org/pdf/1704.00834.pdf)	|	0.86	| 0.71 |
'17-CVPR	| 17/04/11	| [EAST: An Efficient and Accurate Scene Text Detector](https://arxiv.org/pdf/1704.03155.pdf) | | 0.8072	<br> (L)[0.8038](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=29855) | [`TF(M)`](https://github.com/argman/EAST) <br> [`TF`](https://github.com/AKSHAYUBHAT/EAST) <br> [`PYTORCH(M)`](https://github.com/SakuraRiven/EAST) <br> [`PYTORCH`](https://github.com/songdejia/EAST) <br> [`DEMO`](http://east.zxytim.com/) <br> [`KERAS(M)`](https://github.com/kurapan/EAST) <br> [`VIDEO`](https://www.youtube.com/watch?v=o5asMTdhmvA)
'17-ICIP	| 17/05/15	| [WordFence: Text Detection in Natural Images with Border Awareness](https://arxiv.org/pdf/1705.05483.pdf) |	0.86 |
'17-arXiv	| 17/06/30	| [R2CNN: Rotational Region CNN for Orientation Robust Scene Text Detection](https://arxiv.org/pdf/1706.09579.pdf) | 0.8773	| 0.8254 | [`TF(M)`](https://github.com/DetectionTeamUCAS/R2CNN_Faster-RCNN_Tensorflow) <br> [`CAFFE(M)`](https://github.com/beacandler/R2CNN)
'17-CVPR	| 17/07/21	| [Multi-scale FCN with Cascaded Instance Aware Segmentation for Arbitrary Oriented Word Spotting In The Wild](http://openaccess.thecvf.com/content_cvpr_2017/papers/He_Multi-Scale_FCN_With_CVPR_2017_paper.pdf)	|	0.85	| 0.63 | 
'17-arXiv	| 17/08/17	| [Deep Scene Text Detection with Connected Component Proposals](https://arxiv.org/pdf/1708.05133.pdf)	| 0.919 | 
'17-ICCV	| 17/08/22	| [WordSup: Exploiting Word Annotations for Character based Text Detection](https://arxiv.org/pdf/1708.06720) |	0.9064 |	0.7816 |
'17-ICCV	| 17/09/01	| [Single Shot Text Detector with Regional Attention](https://arxiv.org/pdf/1709.00138.pdf)	|	0.8704 |	[0.7691](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=18294) | [`*CAFFE(M)`](https://github.com/BestSonny/SSTD) <br> [`PYTORCH`](https://github.com/HotaekHan/SSTDNet) <br> [`VIDEO`](https://www.youtube.com/watch?v=oBWVgz685-k) 
'17-arXiv	| 17/09/11	| [Fused Text Segmentation Networks for Multi-oriented Scene Text Detection](https://arxiv.org/pdf/1709.03272.pdf) | | [0.8414](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=30447)	|
'17-ICCV	| 17/10/13	| [WeText: Scene Text Detection under Weak Supervision](https://arxiv.org/pdf/1710.04826.pdf)	| 0.869 <br> (L)[0.8313](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=20665) |
'17-ICCV	| 17/10/22	| [Self-organized Text Detection with Minimal Post-processing via Border Learning](http://openaccess.thecvf.com/content_ICCV_2017/papers/Wu_Self-Organized_Text_Detection_ICCV_2017_paper.pdf)	| 0.84 | | [`*KERAS(M)`](https://gitlab.com/rex-yue-wu/ISI-PPT-Text-Detector)
'17-ICDAR	| 17/11/11	| [Deep Residual Text Detection Network for Scene Text](https://arxiv.org/pdf/1711.04147.pdf)	|	0.9117 <br> (L)[0.8925](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=21966) | 
'18-AAAI	| 17/11/12	| [Feature Enhancement Network: A Refined Scene Text Detector](https://arxiv.org/pdf/1711.04249.pdf)	| [0.9161](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=28362) |
'17-arXiv	| 17/11/30	| [ArbiText: Arbitrary-Oriented Text Detection in Unconstrained Scene](https://arxiv.org/pdf/1711.11249.pdf)	|	| 0.759 |	
'18-AAAI	| 18/01/04	| [PixelLink: Detecting Scene Text via Instance Segmentation](https://arxiv.org/pdf/1801.01315.pdf)	|	0.881 | [0.8519](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=30576)	| [`*TF(M)`](https://github.com/ZJULearning/pixel_link) [`TF`](https://github.com/BowieHsu/tensorflow_ocr)
'18-CVPR	| 18/01/05	| [FOTS: Fast Oriented Text Spotting with a Unified Network](https://arxiv.org/pdf/1801.01671.pdf)	| [0.925](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=1&m=34624)	| [0.8984](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=34625)	|	[`PYTORCH`](https://github.com/jiangxiluning/FOTS.PyTorch) <br> [`PYTORCH`](https://github.com/xieyufei1993/FOTS) <br> [`VIDEO`](https://www.youtube.com/watch?v=F7TTYlFr2QM) | 
'18-TIP	| 18/01/09	| [TextBoxes++: A Single-Shot Oriented Scene Text Detector](https://arxiv.org/pdf/1801.02765.pdf)	| 0.88	| 0.829 <br> (L)[0.8475](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=29660) | [`*CAFFE(M)`](https://github.com/MhLiao/TextBoxes_plusplus)
'18-CVPR	| 18/03/09	| [An end-to-end TextSpotter with Explicit Alighment and Attention](https://arxiv.org/pdf/1803.03474.pdf)	| 0.9	| 0.87 |[`*CAFFE(M)`](https://github.com/tonghe90/textspotter)
'18-CVPR	| 18/03/14	| [Rotation-Sensitive Regression for Oriented Scene Text Detection](https://arxiv.org/pdf/1803.05265.pdf)	| 0.89	| 0.838 |	[`*CAFFE(M)`](https://github.com/MhLiao/RRD)
'18-arXiv	| 18/04/08	| [Detecting Multi-Oriented Text with Corner-based Region Proposals](https://arxiv.org/pdf/1804.02690.pdf) | 0.876	| 0.845 | [`*CAFFE(M)`](https://github.com/xhzdeng/crpn)
'18-arXiv	| 18/04/24	| [An Anchor-Free Region Proposal Network for Faster R-CNN based Text Detection Approaches](https://arxiv.org/pdf/1804.09003.pdf)	| 0.92	| 0.86	|
'18-IJCAI	| 18/05/03	| [IncepText: A New Inception-Text Module with Deformable PSROI Pooling for Multi-Oriented Scene Text Detection](https://arxiv.org/pdf/1805.01167.pdf)	| | [0.9047](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=34989) |	
'18-arXiv	| 18/06/07	| [Shape Robust Text Detection with Progressive Scale Expansion Network](https://arxiv.org/pdf/1806.02559.pdf) | |		[0.8721](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=1&m=37493)	| [`PRJ`](https://github.com/whai362/PSENet)
'18-ECCV	| 18/07/04	| [TextSnake: A Flexible Representation for Detecting Text of Arbitrary Shapes](https://arxiv.org/pdf/1807.01544.pdf) | |	0.826	| [`PYTORCH`](https://github.com/princewang1994/TextSnake.pytorch)
'18-ECCV	| 18/07/06	| [Mask TextSpotter: An End-to-End Trainable Neural Network for Spotting Text with Arbitrary Shapes](https://arxiv.org/pdf/1807.02242.pdf) | 0.917	| 0.86 |
'18-ECCV	| 18/07/10	| [Accurate Scene Text Detection through Border Semantics Awareness and Bootstrapping](https://arxiv.org/pdf/1807.03547.pdf) |	0.892	|
'19-AAAI    | 18/11/21  | [Scene Text Detection with Supervised Pyramid Context Network](https://arxiv.org/pdf/1811.08605.pdf)  | 0.921 | 0.872 | 
'19-TIP | 18/12/04 | [TextField: Learning A Deep Direction Field for Irregular Scene Text Detection](https://arxiv.org/pdf/1812.01393.pdf) | | 0.824 | [`*CAFFE(M)`](https://github.com/YukangWang/TextField)
'19-CVPR | 19/03/21 | [Towards Robust Curve Text Detection with Conditional Spatial Expansion](https://arxiv.org/pdf/1903.08836.pdf) | | | |  
'19-CVPR | 19/03/28 | [Shape Robust Text Detection with Progressive Scale Expansion Network](https://arxiv.org/pdf/1903.12473.pdf) | | 0.857 | [`TF(M)`](https://github.com/liuheng92/tensorflow_PSENet)
'19-CVPR | 19/04/03 | [Character Region Awareness for Text Detection](https://arxiv.org/pdf/1904.01941.pdf) | 0.952 | 0.869 |[`*PYTORCH(M)`](https://github.com/clovaai/CRAFT-pytorch) <br> [`VIDEO`](https://www.youtube.com/watch?v=HI8MzpY8KMI) <br> [`PYTORCH`](https://github.com/guruL/Character-Region-Awareness-for-Text-Detection-) <br> [`KERAS`](https://github.com/RubanSeven/CRAFT_keras) <br> [`BLOG_CH`](https://medium.com/@xiaosean5408/craft簡介-character-region-awareness-for-text-detection-a5c782408f00) <br> [`BLOG_KR`](https://data-newbie.tistory.com/187) <br> [`BLOG_KR`](https://medium.com/qandastudy/character-region-awareness-for-text-detection-craft-review-a7542779e037) <br> [`BLOG_KR`](https://github.com/chullhwan-song/Reading-Paper/issues/136)|  
'19-CVPR | 19/04/13 | [Look More Than Once: An Accurate Detector for Text of Arbitrary Shapes Screen reader support enabled](https://arxiv.org/pdf/1904.06535.pdf) | | 0.877 | |  
'19-CVPR | 19/06/16 | [Learning Shape-Aware Embedding for Scene Text Detection](http://jiaya.me/papers/textdetection_cvpr19.pdf) | | 0.877 | |  
'19-CVPR | 19/06/16 | [Arbitrary Shape Scene Text Detection with Adaptive Text Region Representation](https://arxiv.org/pdf/1905.05980.pdf) | 0.917 | 0.876 | |  


## 文本识别
* Score是识别任务中的单词准确率

![avatar](images/recognition_ic13_results.png)
![avatar](images/recognition_iiit5k_results.png)

*Conf.* | *Date* | *Title* | *SVT* | *IIIT5k* | *IC03* | *IC13* | *Resources* |
:---: | :---: |:--- | :---: | :---: | :---: | :---: | :---: |
'15-ICLR	| 14/12/18	| [Deep structured output learning for unconstrained text recognition](https://arxiv.org/pdf/1412.5903.pdf) |	0.717 | |0.896	| 0.818 | [`TF`](https://github.com/AlexandreSev/Structured_Data) <br> [`SLIDE`](https://www.robots.ox.ac.uk/~vgg/publications/2015/Jaderberg15a/presentation.pdf) <br> [`VIDEO`](https://www.youtube.com/watch?v=NYkG38RCoRg)
'16-IJCV	| 15/05/07	| [Reading text in the wild with convolutional neural networks](https://arxiv.org/pdf/1412.1842.pdf)	| 0.807	|	| 	0.933	| 0.908 | [`KERAS`](https://github.com/mathDR/reading-text-in-the-wild)
'16-AAAI	| 15/06/14	| [Reading Scene Text in Deep Convolutional Sequences](https://arxiv.org/pdf/1506.04395.pdf)
'17-TPAMI	| 15/07/21	| [An end-to-end trainable neural network for image-based sequence recognition and its application to scene text recognition](https://arxiv.org/pdf/1507.05717.pdf)	| 0.808	| 0.782 | 0.894	| 0.867 | [`TORCH(M)`](https://github.com/bgshih/crnn)  <br> [`TF`](https://github.com/weinman/cnn_lstm_ctc_ocr)  <br> [`TF`](https://github.com/watsonyanghx/CNN_LSTM_CTC_Tensorflow) <br> [`TF`](https://github.com/MaybeShewill-CV/CRNN_Tensorflow) <br> [`TF`](https://github.com/bai-shang/OCR_TF_CRNN_CTC) <br> [`PYTORCH`](https://github.com/meijieru/crnn.pytorch)  <br> [`PYTORCH(M)`](https://github.com/BelBES/crnn-pytorch) <br> [`BLOG(KR)`](https://medium.com/@mldevhong/%EB%85%BC%EB%AC%B8-%EB%B2%88%EC%97%AD-rcnn-an-end-to-end-trainable-neural-network-for-image-based-sequence-recognition-and-its-f6456886d6f8)
'16-CVPR	| 16/03/09  | [Recursive Recurrent Nets with Attention Modeling for OCR in the Wild](https://arxiv.org/pdf/1603.03101.pdf) |	0.807 | 0.784	| 0.887	| 0.9 |
'16-CVPR	| 16/03/12	| [Robust scene text recognition with automatic rectification](https://arxiv.org/pdf/1603.03915.pdf) |	0.819	| 0.819 | 0.901	| 0.886 | [`PYTORCH`](https://github.com/marvis/ocr_attention) <br> [`PYTORCH`](https://github.com/WarBean/tps_stn_pytorch) 
'16-CVPR	| 16/06/27	| [CNN-N-Gram for Handwriting Word Recognition](https://www.cs.tau.ac.il/~wolf/papers/CNNNGram.pdf) |	0.8362 | | | | [`VIDEO`](https://www.youtube.com/watch?v=czc2Ipm3Bis)
'16-BMVC	| 16/09/19	| [STAR-Net: A SpaTial Attention Residue Network for Scene Text Recognition](http://www.visionlab.cs.hku.hk/publications/wliu_bmvc16.pdf) |	0.836	| 0.833	|	0.899	| 0.891 |
'17-arXiv	| 17/07/27	| [STN-OCR: A single Neural Network for Text Detection and Text Recognition](https://arxiv.org/pdf/1707.08831.pdf) | 0.798	| 0.86	| |	0.903 | [`*MXNET(M)`](https://github.com/Bartzi/stn-ocr) <br> [`PRJ`](https://bartzi.de/research/stn-ocr) <br> [`BLOG`](https://medium.com/@Synced/stn-ocr-a-single-neural-network-for-text-detection-and-text-recognition-220debe6ded4)
'17-IJCAI	| 17/08/19	| [Learning to Read Irregular Text with Attention Mechanisms](https://faculty.ist.psu.edu/zzhou/paper/IJCAI17-IrregularText.pdf) |
'17-arXiv	| 17/09/06	| [Scene Text Recognition with Sliding Convolutional Character Models](https://arxiv.org/pdf/1709.01727.pdf) |	0.765	| 0.816	| 0.845 |	0.852 |
'17-ICCV	| 17/09/07	| [Focusing Attention: Towards Accurate Text Recognition in Natural Images](https://arxiv.org/pdf/1709.02054.pdf) |	0.859 | 0.874 | 0.942 |	0.933 |
'18-CVPR	| 17/11/12	| [AON: Towards Arbitrarily-Oriented Text Recognition](https://arxiv.org/pdf/1711.04226.pdf) |	0.828	|0.87	| 0.915	||[`TF`](https://github.com/huizhang0110/AON)
'17-NIPS	| 17/12/04	| [Gated Recurrent Convolution Neural Network for OCR](https://papers.nips.cc/paper/6637-gated-recurrent-convolution-neural-network-for-ocr.pdf)	| 0.815	| 0.808 | 0.978 | | [`*TORCH(M)`](https://github.com/Jianfeng1991/GRCNN-for-OCR)
'18-AAAI	| 18/01/04	| [Char-Net: A Character-Aware Neural Network for Distorted Scene Text Recognition](http://www.visionlab.cs.hku.hk/publications/wliu_aaai18.pdf) |	0.844	| 0.836	| 0.915 |	0.908 |
'18-AAAI	| 18/01/04	| [SqueezedText: A Real-time Scene Text Recognition by Binary Convolutional Encoder-decoder Network](https://pdfs.semanticscholar.org/0e59/f7d7e9c9380b425a94038c7a2500b2f6063a.pdf) | |	0.87	| 0.931 |	0.929 |
'18-CVPR	| 18/05/09  | [Edit Probability for Scene Text Recognition](https://arxiv.org/pdf/1805.03384.pdf) | 0.875 | 0.883 | 0.946 | 0.944 |
'18-TPAMI	| 18/06/25	| [ASTER: An Attentional Scene Text Recognizer with Flexible Rectification](http://122.205.5.5:8071/UpLoadFiles/Papers/ASTER_PAMI18.pdf) |	0.936	| 0.934 |	0.945	| 0.918	| [`*TF(M)`](https://github.com/bgshih/aster) <br> [`PYTORCH`](https://github.com/ayumiymk/aster.pytorch)
'18-ECCV	| 18/09/08	| [Synthetically Supervised Feature Learning for Scene Text Recognition](http://openaccess.thecvf.com/content_ECCV_2018/papers/Yang_Liu_Synthetically_Supervised_Feature_ECCV_2018_paper.pdf) |	0.871	| 0.894	| 	0.947	| 0.94 |
'19-AAAI    | 18/09/18  | [Scene Text Recognition from Two-Dimensional Perspective](https://arxiv.org/pdf/1809.06508.pdf)   | 0.821 | 0.92 | | 0.914 |
'19-CVPR    | 18/12/14  | [ESIR: End-to-end Scene Text Recognition via Iterative Image Rectification](https://arxiv.org/pdf/1812.05824.pdf)   | 0.902 | 0.933 |  | 0.913 | [PRJ](https://github.com/fnzhan/ESIR)  
'19-PR    | 19/01/10  | [MORAN: A Multi-Object Rectified Attention Network for Scene Text Recognition](https://arxiv.org/pdf/1901.03003.pdf)   | 0.883 | 0.912 | 0.950 | 0.924 | [`*PYTORCH(M)`](https://github.com/Canjie-Luo/MORAN_v2)  
'19-ICCV | 19/04/03 | [What is wrong with scene text recognition model comparisons? dataset and model analysis](https://arxiv.org/pdf/1904.01906.pdf) | 0.875 | | 0.949 | 0.936 | [`*PYTORCH(M)`](https://github.com/clovaai/deep-text-recognition-benchmark) <br> [`BLOG_KR`](https://data-newbie.tistory.com/156)
'19-CVPR | 19/04/18 | [Aggregation Cross-Entropy for Sequence Recognition](https://arxiv.org/pdf/1904.08364.pdf) | 0.826 | 0.823 | 0.921 | 0.897 | [`*PYTORCH`](https://github.com/summerlvsong/Aggregation-Cross-Entropy) | 
'19-CVPR | 19/06/16 | [Sequence-to-Sequence Domain Adaptation Network for Robust Text Image Recognition](http://openaccess.thecvf.com/content_CVPR_2019/papers/Zhang_Sequence-To-Sequence_Domain_Adaptation_Network_for_Robust_Text_Image_Recognition_CVPR_2019_paper.pdf) | 0.845 | 0.838 | 0.921 | 0.918 | |


## 端到端文本识别
* Score 是一般任务的F1-Score 

![avatar](images/end2end_ic13_ic15_results.png)

*Conf.* | *Date* | *Title* | *IC03* | *IC13* | *IC15* | *Resources* |
:---: | :---: |:--- | :---: | :---: | :---: | :---: |
'12-ICPR    | 12/11/11  | [End-to-end text recognition with convolutional neural networks](https://ai.stanford.edu/~ang/papers/ICPR12-TextRecognitionConvNeuralNets.pdf)    | 0.67 | | | [`*CODE`](http://cs.stanford.edu/people/twangcat/ICPR2012_code/SceneTextCNN_demo.tar)
'14-ECCV    | 14/09/06  | [Deep Features for Text Spotting](https://www.robots.ox.ac.uk/~vgg/publications/2014/Jaderberg14/jaderberg14.pdf) | 0.75  | | | [`PRJ`](http://www.robots.ox.ac.uk/~vgg/research/text/) <br> [`MATLAB`](https://bitbucket.org/jaderberg/eccv2014_textspotting)
'15-IJCV    | 15/05/07  | [Reading Text in the Wild with Convolutional Neural Networks](https://arxiv.org/pdf/1412.1842.pdf)    | 0.70  | 0.77 | | [`KERAS`](https://github.com/mathDR/reading-text-in-the-wild)
'15-TPAMI   | 15/10/30  | [Real-time Lexicon-free Scene Text Localization and Recognition](http://cmp.felk.cvut.cz/~neumalu1/Neumann_TPAMI2015.pdf) | | 0.542 | 0.156 |
'16-arXiv   | 16/04/10  | [TextProposals: a Text-specific Selective Search Algorithm for Word Spotting in the Wild](https://arxiv.org/pdf/1604.02619.pdf) | | 0.6843 | 0.4718 <br> (L)[0.533](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=4&m=7807) | [`*CAFFE(M)`](https://github.com/lluisgomez/TextProposals)
'17-AAAI    | 16/11/21  | [TextBoxes: A fast text detector with a single deep neural network](https://arxiv.org/pdf/1611.06779.pdf) | | 0.84 | | [`TF`](https://github.com/shinjayne/shinTB) <br> [`*CAFFE(M)`](https://github.com/MhLiao/TextBoxes) <br> [`BLOG_KR`](http://jaynewho.com/post/6)
'17-ICCV    | 17/07/13  | [Towards End-to-end Text Spotting with Convolution Recurrent Neural Network](https://arxiv.org/pdf/1707.03985.pdf) | | 0.8459 | | [`VIDEO`](https://www.youtube.com/watch?v=j0guWqBJ0lA)
'17-ICCV    | 17/10/22  | [Deep TextSpotter An End-to-End Trainable Scene Text Localization and Recognition Framework](http://openaccess.thecvf.com/content_ICCV_2017/papers/Busta_Deep_TextSpotter_An_ICCV_2017_paper.pdf) | | 0.77 | 0.47 | [`VIDEO`](https://www.youtube.com/watch?v=VcNSQGO0j7s) <br> [`*CAFFE(M)`](https://github.com/MichalBusta/DeepTextSpotter)
'18-CVPR    | 18/01/05  | [FOTS: Fast Oriented Text Spotting with a Unified Network](https://arxiv.org/pdf/1801.01671.pdf) | | [0.8477](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=4&m=34627) | [0.6533](http://rrc.cvc.uab.es/?ch=4&com=evaluation&view=method_info&task=4&m=34626) | [`VIDEO`](https://www.youtube.com/watch?v=F7TTYlFr2QM) <br> [`TF(M)`](https://github.com/Pay20Y/FOTS_TF)
'18-TIP     | 18/01/09  | [TextBoxes++: A Single-Shot Oriented Scene Text Detector](https://arxiv.org/pdf/1801.02765.pdf) | | [0.8465](http://rrc.cvc.uab.es/?ch=2&com=evaluation&view=method_info&task=4&m=27895) | 0.519 | [`*CAFFE(M)`](https://github.com/MhLiao/TextBoxes_plusplus)
'18-CVPR    | 18/03/09  | [An end-to-end TextSpotter with Explicit Alighment and Attention](https://arxiv.org/pdf/1803.03474.pdf) | | 0.86 | 0.63 | [`*CAFFE(M)`](https://github.com/tonghe90/textspotter)
'18-TPAMI   | 18/06/25  | [ASTER: An Attentional Scene Text Recognizer with Flexible Rectification](http://122.205.5.5:8071/UpLoadFiles/Papers/ASTER_PAMI18.pdf) | | | 0.64 | [`*TF(M)`](https://github.com/bgshih/aster)
'18-ECCV    | 18/07/06  | [Mask TextSpotter: An End-to-End Trainable Neural Network for Spotting Text with Arbitrary Shapes](https://arxiv.org/pdf/1807.02242.pdf) | | 0.865 | 0.624 |

## 其他会议和论文

*Conf.* | *Date* | *Title* | *Description* | *Resources* |
:---: | :---: |:--- | :---: | :---: |
'14-NIPS	| 14/06/09  |   [Synthetic Data and Artificial Neural Networks for Natural Scene Text Recognition](https://arxiv.org/pdf/1406.2227.pdf) |	Dataset | [`PRJ`](http://www.robots.ox.ac.uk/~vgg/data/text/)
'17-ECCV	| 17/02/13  |	[End-to-End Interpretation of the French Street Name Signs Dataset](https://arxiv.org/pdf/1702.03970.pdf) |	Dataset (FSNS) | [`*TF(M)`](https://github.com/tensorflow/models/tree/master/research/attention_ocr)
'17-arXiv	| 17/04/11	|	[Attention-based Extraction of Structured Information from Street View Imagery](https://arxiv.org/pdf/1704.03549.pdf) |	FSNS | [`*TF(M)`](https://github.com/tensorflow/models/tree/master/research/attention_ocr) <br> [`TF`](https://github.com/da03/Attention-OCR) <br> [`TF`](https://github.com/emedvedev/attention-ocr) <br> [`LUA`](https://github.com/da03/torch-Attention-OCR) <br> [`BLOG_KR`](https://norman3.github.io/papers/docs/attention_ocr.html)
'17-CVPR	| 17/07/21	|	[Unambiguous Text Localization and Retrieval for Cluttered Scenes](http://openaccess.thecvf.com/content_cvpr_2017/papers/Rong_Unambiguous_Text_Localization_CVPR_2017_paper.pdf) |	Text Retrieval
'17-AAAI	| 17/10/22	|	[Detection and Recognition of Text Embedded in Online Images via Neural Context Models](http://s-space.snu.ac.kr/bitstream/10371/116866/1/aaai2017_cameraready.pdf) |	Dataset | [`PRJ`](https://github.com/cmkang/CTSN)
'18-CVPR	| 17/11/17	|	[Separating Style and Content for Generalized Style Transfer](https://arxiv.org/pdf/1711.06454.pdf) |	Font Style
'17-arXiv	| 17/12/06	|	[Detecting Curve Text in the Wild New Dataset and New Solution](https://arxiv.org/pdf/1712.02170.pdf) |	Dataset (CTW 1500) | [`PRJ`](https://github.com/Yuliang-Liu/Curve-Text-Detector)
'18-AAAI	| 17/12/14	|	[SEE: Towards Semi-Supervised End-to-End Scene Text Recognition](https://arxiv.org/pdf/1712.05404.pdf) |	FSNS | [`PRJ`](https://bartzi.de/research/see) <br> [`*CHAINER(M)`](https://github.com/Bartzi/see)
'17-CVPR	| 18/06/07	|	[Learning to Extract Semantic Structure from Documents Using Multimodal Fully Convolutional Neural Networks](https://arxiv.org/pdf/1706.02337.pdf) |	Document Layout | [`PRJ`](http://personal.psu.edu/xuy111/projects/cvpr2017_doc.html)
'18-CVPR	| 18/06/19	|	[DocUNet: Document Image Unwarping via A Stacked U-Net](http://www.juew.org/publication/DocUNet.pdf) |	Document Dewarping | [`PRJ`](http://www3.cs.stonybrook.edu/~cvl/docunet.html)
'18-CVPR	| 18/06/19	|	[Document Enhancement using Visibility Detection](http://webee.technion.ac.il/~ayellet/Ps/18-KKT.pdf) |	Document Enhancement | [`PRJ`](http://cgm.technion.ac.il/Computer-Graphics-Multimedia/Software/VisibilityDetection/)
'18-IJCAI	| 18/06/22	|	[Multi-Task Handwritten Document Layout Analysis](https://arxiv.org/pdf/1806.08852.pdf) |	Document Layout
'18-ECCV	| 18/07/09	|	[Verisimilar Image Synthesis for Accurate Detection and Recognition of Texts in Scenes](https://arxiv.org/pdf/1807.03021.pdf) |	Dataset | [`PRJ`](https://github.com/fnzhan/Verisimilar-Image-Synthesis-for-Accurate-Detection-and-Recognition-of-Texts-in-Scenes)
'19-AAAI	| 18/12/03  |	[EnsNet: Ensconce Text in the Wild](https://arxiv.org/pdf/1812.00723.pdf) | Text Removal |	[`DB`](https://github.com/HCIILAB/Scene-Text-Removal)  
'19-CVPR	| 18/12/14  |	[Spatial Fusion GAN for Image Synthesis](https://arxiv.org/pdf/1812.05840.pdf) | Dataset |	[`DB`](https://github.com/fnzhan/SF-GAN)  
'19-AAAI	| 19/01/27  |	[Hierarchical Encoder with Auxiliary Supervision for Table-to-text Generation: Learning Better Representation for Tables](https://www.aaai.org/Papers/AAAI/2019/AAAI-LiuT.3205.pdf) | TableToText |	  
'19-AAAI	| 19/01/27  |	[A Radical-aware Attention-based Model for Chinese Text Classification](https://www.aaai.org/Papers/AAAI/2019/AAAI-TaoH.5441.pdf) | Chinese Character Classification |	  
'19-AAAI	| 19/01/27  |	[Hierarchical Encoder with Auxiliary Supervision for Table-to-text Generation: Learning Better Representation for Tables](https://www.aaai.org/Papers/AAAI/2019/AAAI-LiuT.3205.pdf) | TableToText |	  
'19-CVPR | 19/02/25 | [Handwriting Recognition in Low-resource Scripts using Adversarial Learning](https://arxiv.org/pdf/1811.01396.pdf) | Handwritting Recognition | [`TF`](https://github.com/AyanKumarBhunia/Handwriting_Recogition_using_Adversarial_Learning)
'19-CVPR	| 19/03/27  |	[Tightness-aware Evaluation Protocol for Scene Text Detection](https://arxiv.org/pdf/1904.00813.pdf) | Evaluation |	[`CODE`](https://github.com/Yuliang-Liu/TIoU-metric)  
'19-CVPR	| 19/06/16  |	[DynTypo: Example-based Dynamic Text Effects Transfer](https://menyifang.github.io/projects/DynTypo/DynTypo_files/Paper_DynTypo_CVPR19.pdf) | Text Effects |	[`PRJ`](https://menyifang.github.io/projects/DynTypo/DynTypo.html) <br> [`VIDEO`](https://youtu.be/FkFQ6bV1s-o) 
'19-CVPR | 19/06/16 | [Typography with Decor: Intelligent Text Style Transfer](http://openaccess.thecvf.com/content_CVPR_2019/papers/Wang_Typography_With_Decor_Intelligent_Text_Style_Transfer_CVPR_2019_paper.pdf) | Text Effects | [`*PYTORCH(M)`](https://daooshee.github.io/Typography2019/) 
'19-CVPR | 19/06/16 | [An Alternative Deep Feature Approach to Line Level Keyword Spotting](http://openaccess.thecvf.com/content_CVPR_2019/papers/Retsinas_An_Alternative_Deep_Feature_Approach_to_Line_Level_Keyword_Spotting_CVPR_2019_paper.pdf) | Kyeword Spotting


## 论文和代码
### 综述
  - [Scene Text Detection and Recognition:The Deep Learning Era](https://arxiv.org/pdf/1811.04256.pdf)
  - [Scene text detection and recognition: recent advances and future trends](https://www.researchgate.net/profile/Xiang_Bai4/publication/286945604_Scene_text_detection_and_recognition_recent_advances_and_future_trends/links/57f720f408ae886b8981d364/Scene-text-detection-and-recognition-recent-advances-and-future-trends.pdf) 
  - [Deep Neural Networks for Scene Text Reading (IC17 Keynote)](http://u-pat.org/ICDAR2017/keynotes/ICDAR2017_Keynote_Prof_Bai.pdf)
  - [Oriented Scene Text Detection Revisited (VALSE17 Invited Talk)](http://cloud.eic.hust.edu.cn:8071/~xbai/Talk_slice/Oriented-Scene-Text-Detection-Revisited_VALSE2017.pdf)
  - [Scene Text Detection and Recognition (Joint course of Megvii Inc. & Peking Univ.)](https://zsc.github.io/megvii-pku-dl-course/slides/Lecture7(Text%20Detection%20and%20Recognition_20171031).pdf)
  - [Classic Text Detectors](https://www.slideshare.net/anyline_io/text-detection-strategies)

### 按年份分
  - [2019-present](papers/papers_by_year/2019-present.md)
  - [2015-2018](papers/papers_by_year/2015-2018.md)
  - [2011-2014](papers/papers_by_year/2011-2014.md)
  - [before-2010](papers/papers_by_year/before-2010.md)

### 按任务分
  - [overview](papers/papers_by_topics/overview.md)
  - [text-detection](papers/papers_by_topics/text-detection.md)
  - [text-recognition](papers/papers_by_topics/text-recognition.md)
  - [text-segmentation](papers/papers_by_topics/text-segmentation.md)
  - [end-to-end-ocr](papers/papers_by_topics/end-to-end-ocr.md)
  - [video-ocr](papers/papers_by_topics/video-ocr.md)
  - [document-image-unwarping](papers/papers_by_topics/document-image-unwarping.md)

### 按会议和期刊分
  - [CVPR: IEEE Conference on Computer Vision and Pattern Recognition](papers/papers_by_conferences_and_journals/CVPR.md)
  - [NIPS: Neural Information Processing Systems](papers/papers_by_conferences_and_journals/NIPS.md)
  - [ECCV: European Conference on Computer Vision](papers/papers_by_conferences_and_journals/ECCV.md)
  - [ICCV: International Conference on Computer Vision](papers/papers_by_conferences_and_journals/ICCV.md)
  - [ICLR: International Conference on Learning Representations](papers/papers_by_conferences_and_journals/ICLR.md)
  - [AAAI: Association for the Advancement of Artificial Intelligence](papers/papers_by_conferences_and_journals/AAAI.md)
  - [IJCAI: International Joint Conference on Artificial Intelligence](papers/papers_by_conferences_and_journals/IJCAI.md)
  - [BMVC: British Machine Vision Conference](papers/papers_by_conferences_and_journals/BMVC.md)
  - [ICPR: International Conference on Pattern Recognition](papers/papers_by_conferences_and_journals/ICPR.md)
  - [ICDAR: International Conference on Document Analysis and Recognition](papers/papers_by_conferences_and_journals/ICDAR.md)
  - [TPAMI: IEEE Transactions on Pattern Analysis and Machine Intelligence](papers/papers_by_conferences_and_journals/TPAMI.md)
  - [IJCV: International Journal of Computer Vision](papers/papers_by_conferences_and_journals/IJCV.md)
  - [TIP: IEEE Transactions on Image Processing](papers/papers_by_conferences_and_journals/TIP.md)
  - [TMM: IEEE Transactions on Multimedia](papers/papers_by_conferences_and_journals/TMM.md)

## 数据集
  - [ICDAR会议基准数据集](datasets/ICDAR_DATA)
  - [自然场景数据集](datasets/NATURAL_DATA)
  - [人工数据集](datasets/SYNTH_DATA)
  - [不规则文本数据集](datasets/IRREGULAR_DATA)
  - [单词/字符数据集](datasets/WORD_DATA)
  - [视频数据集](datasets/VIDEO_DATA)
  - [其他](datasets/Others)
### 数据集对比
| 数据集(年份) | 图片数量 (train/test) | 文本数量 (train/test) | 文字方向| 语言| 特点 | 文本检测/识别 任务 |
|:------:|:------:|:------:|:------:|:------:|:------:|:------:|
|End2End|====|====|====|====|====|====|
| [ICDAR03 (2003)](http://www.iapr-tc11.org/mediawiki/index.php?title=ICDAR_2003_Robust_Reading_Competitions) | 509 (258/251) | 2276 (1110/1156) | 水平 | En | - | ✓/✓ |
| [ICDAR13 Scene Text(2013)](http://dagdata.cvc.uab.es/icdar2013competition/) | 462 (229/233) | - (848/1095) | 水平 | En | 自然场景 | ✓/✓ |
| [ICDAR15 Incidental Text(2015)](http://rrc.cvc.uab.es/?ch=4&com=introduction) | 1500 (1000/500) | - (-/-) | 多方向 | En |  图片模糊且非刻意拍摄 | ✓/✓ |
| [ICDAR17 / RCTW (2017)](http://rctw.vlrlab.net/dataset/) | 12263 (8034/4229) | - (-/-) | 多方向 | Cn | 手机相机拍摄，手机屏幕截图 | ✓/✓ |
| [CoCo-Text v2.0 (2019)](http://vision.cornell.edu/se3/coco-text-2/) | 63686 (-/-) | 239506 (-/-) | 多方向 | En | 在线数据集，标注详细 | ✓/✓ |
| [Total-Text (2017)](https://github.com/cs-chan/Total-Text-Dataset) | 1555 (1255/300) | 11459 (-/-) | 多方向，  弯曲 | En， Cn | 文本不规则，使用多边形标注 | ✓/✓ |
| [SVT (2010)](http://www.iapr-tc11.org/mediawiki/index.php?title=The_Street_View_Text_Dataset) | 350 (100/250) | 904 (257/647) | 水平| En| 谷歌街景 | ✓/✓ |
| [KAIST (2010)](http://www.iapr-tc11.org/mediawiki/index.php?title=KAIST_Scene_Text_Database) | 3000 (-/-) | 5000 (-/-) | 水平| En， Ko| 数据集分类详细 | ✓/✓ |
| [NEOCR (2011)](http://www.iapr-tc11.org/mediawiki/index.php?title=NEOCR:_Natural_Environment_OCR_Dataset) | 659 (-/-) | 5238 (-/-) | 多方向| 8 langs| 自然场景 | ✓/✓ |
| [CTW (2017)](https://ctwdataset.github.io) |  32K ( 25K/6K) |  1M ( 812K/205K) | 多方向 | Cn |  中文街景，图片高清，标注详细 | ✓/✓ |
| [CASIA-10K (2018)](https://github.com/Jyouhou/SceneTextPapers/blob/master/datasets/CASIA-10K.md) | 10K (7K/3K) | - (-/-) | 多方向 | Cn | 场景文本检测 | ✓/✓ |
| [SDTL (2016)](https://github.com/ankush-me/SynthText) |  自定(-/-) |  90k(-/-) | 水平| -| 在自然场景图片内人工合成文本，提供源码 | ✓/√ |
|仅文本检测|====|====|====|====|====|====|
| [MSRA-TD500 (2012)](http://www.iapr-tc11.org/mediawiki/index.php/MSRA_Text_Detection_500_Database_(MSRA-TD500)) | 500 (300/200) | 1719 (1068/651) |  多方向 | En， Cn |  自然场景 | ✓/- |
| [ICDAR17 / RRC-MLT (2017)](http://rrc.cvc.uab.es/?ch=8) | 18000 (9000/9000) | - (-/-) | 多方向 |  9 langs | 自然场景 | ✓/- |
| [SCUT-CTW1500 (2017)](https://github.com/Yuliang-Liu/Curve-Text-Detector) | 1500 (1000/500) | - (-/-) | 多方向，弯曲 | En，Cn | 用于各种形状的文本检测 | ✓/- |
|仅文本识别|====|====|====|====|====|====|
| [Char74k (2009)](http://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/) | 74107 (-/-) | 74107 (-/-) | 水平| En， Kannada | 全部为单字符 | -/✓ |
| [IIIT 5K-Word (2012)](http://cvit.iiit.ac.in/projects/SceneTextUnderstanding/IIIT5K.html) | 5000 (-/-) | 5000 (2000/3000) | 水平| -| 字符边缘有干扰 | -/✓ |
| [SVHN (2010)](http://www.iapr-tc11.org/mediawiki/index.php?title=The_Street_View_House_Numbers_(SVHN)_Dataset) | 99290 (73258/26032) |  (-/-) | 水平| -| 全部为街景中的数字图片 | -/✓ |
| [SWD (2014)](http://www.robots.ox.ac.uk/~vgg/data/text/) | 900w (-/-) |  90k(-/-) | 水平| -| 全部为人工合成的文本 | -/✓ |

## 其他资源
  - [whitelok](https://github.com/whitelok/image-text-localization-recognition)
  - [tangzhenyu](https://github.com/tangzhenyu/Scene-Text-Understanding)
  - [wanghaisheng](https://github.com/wanghaisheng/awesome-ocr)
  - [ChanChiChoi](https://github.com/ChanChiChoi/awesome-ocr/blob/master/README.md)
  - [handong1587](https://github.com/handong1587/handong1587.github.io/blob/master/_posts/deep_learning/2015-10-09-ocr.md)
  - [hs105](https://github.com/hs105/Deep-Learning-for-OCR)


