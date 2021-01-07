This is forked from [这里](https://github.com/AlanLuSun/High-quality-ellipse-detection)。椭圆特征在机器视觉中经常出现，对于椭圆中心的高精度检测，时长会有用到。至于如何高精度地绘制椭圆，可以参考我的分享：[高精度绘制椭圆demo](https://github.com/qxiaofan/awesome-draw-precise-ellipse)

# High-quality Ellipse Detection

## 1. Illustration
- This is the source code for the paper [Arc-support Line Segments Revisited: An Efficient and High-quality Ellipse Detection](https://arxiv.org/abs/1810.03243). ***Important: Please use the citation of our IEEE TIP version instead of arXiv version***.
- The main contribution of the proposed ellipse detector is to both accurately and efficiently detect ellipses in images, which is universally considered as a tough and long-standing problem in ellipse detection field. The proposed ellipse detector owns the features of *high localization accuracy, efficiency, robustness*, and *stability*, which comprehensively yields high-quality ellipse detection performance in front of real-world images. 
- There are only *two* extrinsic parameters, namely the elliptic angular coverage $T_{ac}$ and the ratio of support inliers $T_{r}$, which enables the proposed ellipse detector to be conveniently used and applied in real applications. In addition, the *specified_polarity* option can help users find the polarity-specific ellipses in the image. The default parameters $T_{ac} = 165^o$ and $T_{r} = 0.6$ are used for comparison experiments in our paper.  
- The source code is free for academic use. Please cite our paper if you use the source code, thanks.

## 2. Requirements
- MATLAB
- OpenCV (Version 2.4.9)
- 64-bit Windows Operating System


## 3. How to use
- Firstly, compile the file "generateEllipseCandidates.cpp" in MATLAB on your computer to generate the mex file "generateEllipseCandidates.mexw64" with the following command:  
  
  ---
  mex generateEllipseCandidates.cpp -IF:\OpenCV\opencv2.4.9\build\include -IF:\OpenCV\opencv2.4.9\build\include\opencv -IF:\OpenCV\opencv2.4.9\build\include\opencv2 -LF:\OpenCV\opencv2.4.9\build\x64\vc11\lib -IF:\Matlab\settlein\extern\include -LF:\Matlab\settlein\extern\lib\win64\microsoft -lopencv_core249 -lopencv_highgui249 -lopencv_imgproc249 -llibmwlapack.lib  
  
  ---
  Notably, the corresponding software paths of OpenCV and MATLAB, namely the "F:\OpenCV\opencv2.4.9\" and "F:\Matlab\settlein\", should be replaced to your own.  
- Secondly, run the demo file "LCS_ellipse.m".


## 4. Examples
*Some high-quality ellipse detection examples run with default parameters and on the same computer with Intel Core i7-7500U 2.7GHz CPU and 8 GB memory*

### 4.1 Detecting all ellipses in the image

---
- The number of detected ellipses: 4; Running time: 0.090s; Resolution: 651 x 436
  <img src="./pics/43_result.jpg" width="73%" height="73%">  
  
---
- The number of detected ellipses: 25; Running time: 0.460s; Resolution: 720 x 435
  <img src="./pics/27_result.jpg" width="73%" height="73%"> 


---
- The number of detected ellipses: 3; Running time: 0.060s; Resolution: 512 x 456
  <img src="./pics/23_result.jpg" width="73%" height="73%"> 


---
- The number of detected ellipses: 8; Running time: 0.110s; Resolution: 752 x 525
  <img src="./pics/666_result.jpg" width="73%" height="73%"> 


### 4.2 Detecting the ellipses with positive polarity  
- The number of detected ellipses: 4; Running time: 0.080s; Resolution: 752 x 525
  <img src="./pics/666_positive.jpg" width="73%" height="73%"> 

### 4.3 Detecting the ellipses with negative polarity
- The number of detected ellipses: 4; Running time: 0.086s; Resolution: 752 x 525
  <img src="./pics/666_negative.jpg" width="73%" height="73%"> 

### 4.4 Detecting the ellipses sharing different polarity  
- The number of detected ellipses: 5; Running time: 0.226s; Resolution: 1000 x 680. ($T_{ac} = 165^{o}$, $T_r = 0.5$)  
  <img src="./pics/different-polarity-detection_all.jpg" width="73%" height="73%"> 


## 5. Successful Application Cases Up to Now
- Car Wheel Hub Recognition
- PCB Inspection
- Object Fingerprinting
- Robot Vision


## 6. Citation
```
@article{lu2019arc,
  title={Arc-Support Line Segments Revisited: An Efficient High-Quality Ellipse Detection},
  author={Lu, Changsheng and Xia, Siyu and Shao, Ming and Fu, Yun},
  journal={IEEE Transactions on Image Processing},
  volume={29},
  pages={768--781},
  year={2020},
  publisher={IEEE}
}
```

## 7. Our Previous Work  
We also proposed a [circle detection method](https://github.com/AlanLuSun/Circle-detection) in our previous work which could detect circles from image efficiently, precisely and robustly.

### 跋

- [加群](#加群)

<a name="加群"></a>

作者：3D视觉工坊所有投稿作者

来源：公众号|[3D视觉工坊](https://mp.weixin.qq.com/s/weShDMbGTf0amg1qu_t8cw)

![](/home/yong/workspace/2_project_files/0_github_upload_files/vision3d/DrawPreciseEllipse/DrawPreciseEllipse/imgs/公众号.jpg)

「3D视觉工坊」技术交流群已经成立，目前大约有12000人，方向主要涉及3D视觉、CV&深度学习、SLAM、三维重建、点云后处理、自动驾驶、CV入门、三维测量、VR/AR、3D人脸识别、医疗影像、缺陷检测、行人重识别、目标跟踪、视觉产品落地、视觉竞赛、车牌识别、硬件选型、学术交流、求职交流、ORB-SLAM系列源码交流、深度估计等。工坊致力于干货输出，不做搬运工，为计算机视觉领域贡献自己的力量！欢迎大家一起交流成长~

添加小助手微信：CV_LAB，备注学校/公司+姓名+研究方向即可加入工坊一起学习进步。

![](/home/yong/workspace/2_project_files/0_github_upload_files/vision3d/DrawPreciseEllipse/DrawPreciseEllipse/imgs/微信.jpg)

QQ群「3D视觉工坊」，群号：949193717

![](/home/yong/workspace/2_project_files/0_github_upload_files/vision3d/DrawPreciseEllipse/DrawPreciseEllipse/imgs/QQ群.jpg)



备注：

1、[3D视觉招聘信息汇总](https://github.com/qxiaofan/awesome-Computer-Vision-Algorithm-Jobs)

2、[一个超干货的3D视觉学习社区](https://mp.weixin.qq.com/s/weShDMbGTf0amg1qu_t8cw)

