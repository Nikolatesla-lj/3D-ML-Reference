# 3D Machine Learning (Credit: timzhang642, https://github.com/timzhang642/3D-Machine-Learning)
*Note*: For personal collection use. Please go to original author's repository: timzhang642, https://github.com/timzhang642/3D-Machine-Learning if you want to see the new updates. I don't have any credit or any contribution for this repository.'

In recent years, tremendous amount of progress is being made in the field of 3D Machine Learning, which is an interdisciplinary field that fuses computer vision, computer graphics and machine learning. This repo is derived from my study notes and will be used as a place for triaging new research papers. 

I'll use the following icons to differentiate 3D representations:
* :camera: Multi-view Images
* :space_invader: Volumetric
* :game_die: Point Cloud
* :gem: Polygonal Mesh
* :pill: Primitive-based

## Get Involved
To make it a collaborative project, you may add content throught pull requests or open an issue to let me know. 

## Available Courses
[Stanford CS468: Machine Learning for 3D Data (Spring 2017)](http://graphics.stanford.edu/courses/cs468-17-spring/)

[MIT 6.838: Shape Analysis (Spring 2017)](http://groups.csail.mit.edu/gdpgroup/6838_spring_2017.html)

[Princeton COS 526: Advanced Computer Graphics  (Fall 2010)](https://www.cs.princeton.edu/courses/archive/fall10/cos526/syllabus.php)

[Princeton CS597: Geometric Modeling and Analysis (Fall 2003)](https://www.cs.princeton.edu/courses/archive/fall03/cs597D/)

[Geometric Deep Learning](http://geometricdeeplearning.com/)

[Paper Collection for 3D Understanding](https://www.cs.princeton.edu/courses/archive/spring15/cos598A/cos598A.html#Estimating)

## Table of Contents
- [Datasets](#datasets)
  - [3D Models](#3d_models)
  - [3D Scenes](#3d_scenes)
- [Single Object Classification](#single_classification)
- [Multiple Objects Detection](#multiple_detection)
- [Scene/Object Semantic Segmentation](#segmentation)
- [3D Synthesis/Reconstruction](#3d_synthesis)
  - [Parametric Morphable Model-based methods](#3d_synthesis_model_based)
  - [Part-based Template Learning methods](#3d_synthesis_template_based)
  - [Deep Learning Methods](#3d_synthesis_dl_based)
- [Style Transfer](#style_transfer)
- [Scene Synthesis](#scene_synthesis)
- [Scene Understanding](#scene_understanding)

<a name="datasets" />

## Datasets
To see a survey of RGBD datasets, check out Michael Firman's [collection](http://www0.cs.ucl.ac.uk/staff/M.Firman//RGBDdatasets/) as well as the associated paper, [RGBD Datasets: Past, Present and Future](https://arxiv.org/pdf/1604.00999.pdf). Point Cloud Library also has a good dataset [catalogue](http://pointclouds.org/media/). 

<a name="3d_models" />

### 3D Models
<b>Dataset for IKEA 3D models and aligned images (2013)</b> [[Link]](http://ikea.csail.mit.edu/)
<br>759 images and 219 models including Sketchup (skp) and Wavefront (obj) files.
<p align="center"><img width="50%" src="http://ikea.csail.mit.edu/web_img/ikea_object.png" /></p>

<b>PASCAL3D+ (2014)</b> [[Link]](http://cvgl.stanford.edu/projects/pascal3d.html)
<br>12 categories, on average 3k+ objects per category, for 3D object detection and pose estimation.
<p align="center"><img width="50%" src="http://cvgl.stanford.edu/projects/pascal3d+/pascal3d.png" /></p>

<b>ModelNet (2015)</b> [[Link]](http://modelnet.cs.princeton.edu/#)
<br>127915 3D CAD models from 662 categories
<br>ModelNet10: 4899 models from 10 categories
<br>ModelNet40: 12311 models from 40 categories, all are uniformly orientated
<p align="center"><img width="50%" src="http://3dvision.princeton.edu/projects/2014/ModelNet/thumbnail.jpg" /></p>

<b>ShapeNet (2015)</b> [[Link]](https://www.shapenet.org/)
<br>3Million+ models and 4K+ categories. A dataset that is large in scale, well organized and richly annotated.
<br>ShapeNetCore [[Link]](http://shapenet.cs.stanford.edu/shrec16/): 51300 models for 55 categories.
<p align="center"><img width="50%" src="http://msavva.github.io/files/shapenet.png" /></p>

<b>A Large Dataset of Object Scans (2016)</b> [[Link]](http://redwood-data.org/3dscan/index.html)
<br>10K scans in RGBD + reconstructed 3D models in .PLY format.
<p align="center"><img width="50%" src="http://redwood-data.org/3dscan/img/teaser.jpg" /></p>

<b>ObjectNet3D: A Large Scale Database for 3D Object Recognition (2016)</b> [[Link]](http://cvgl.stanford.edu/projects/objectnet3d/)
<br>100 categories, 90,127 images, 201,888 objects in these images and 44,147 3D shapes. 
<br>Tasks: region proposal generation, 2D object detection, joint 2D detection and 3D object pose estimation, and image-based 3D shape retrieval
<p align="center"><img width="50%" src="http://cvgl.stanford.edu/projects/objectnet3d/ObjectNet3D.png" /></p>

<a name="3d_scenes" />

### 3D Scenes

<b>SUNRGB-D 3D Object Detection Challenge</b> [[Link]](http://rgbd.cs.princeton.edu/challenge.html)
<br>19 object categories for predicting a 3D bounding box in real world dimension
<br>Training set: 10,355 RGB-D scene images, Testing set: 2860 RGB-D images
<p align="center"><img width="50%" src="http://rgbd.cs.princeton.edu/3dbox.png" /></p>

<b>SceneNN (2016)</b> [[Link]](http://people.sutd.edu.sg/~saikit/projects/sceneNN/)
<br>100+ indoor scene meshes with per-vertex and per-pixel annotation.
<p align="center"><img width="50%" src="https://cdn-ak.f.st-hatena.com/images/fotolife/r/robonchu/20170611/20170611155625.png" /></p>

<b>ScanNet (2017)</b> [[Link]](http://www.scan-net.org/)
<br>An RGB-D video dataset containing 2.5 million views in more than 1500 scans, annotated with 3D camera poses, surface reconstructions, and instance-level semantic segmentations.
<p align="center"><img width="50%" src="http://www.scan-net.org/img/voxel-predictions.jpg" /></p>

<b>Matterport3D: Learning from RGB-D Data in Indoor Environments (2017)</b> [[Link]](https://niessner.github.io/Matterport/)
<br>10,800 panoramic views (in both RGB and depth) from 194,400 RGB-D images of 90 building-scale scenes of private rooms. Instance-level semantic segmentations are provided for region (living room, kitchen) and object (sofa, TV) categories. 
<p align="center"><img width="50%" src="https://niessner.github.io/Matterport/teaser.png" /></p>

<b>SUNCG: A Large 3D Model Repository for Indoor Scenes (2017)</b> [[Link]](http://suncg.cs.princeton.edu/)
<br>The dataset contains over 45K different scenes with manually created realistic room and furniture layouts. All of the scenes are semantically annotated at the object level.
<p align="center"><img width="50%" src="http://suncg.cs.princeton.edu/figures/data_full.png" /></p>

<b>MINOS: Multimodal Indoor Simulator (2017)</b> [[Link]](https://github.com/minosworld/minos)
<br>MINOS is a simulator designed to support the development of multisensory models for goal-directed navigation in complex indoor environments. MINOS leverages large datasets of complex 3D environments and supports flexible configuration of multimodal sensor suites. MINOS supports SUNCG and Matterport3D scenes.
<p align="center"><img width="50%" src="http://vladlen.info/wp-content/uploads/2017/12/MINOS.jpg" /></p>

<b>Facebook House3D: A Rich and Realistic 3D Environment (2017)</b> [[Link]](https://github.com/facebookresearch/House3D)
<br>House3D is a virtual 3D environment which consists of 45K indoor scenes equipped with a diverse set of scene types, layouts and objects sourced from the SUNCG dataset. All 3D objects are fully annotated with category labels. Agents in the environment have access to observations of multiple modalities, including RGB images, depth, segmentation masks and top-down 2D map views.
<p align="center"><img width="50%" src="https://user-images.githubusercontent.com/1381301/33509559-87c4e470-d6b7-11e7-8266-27c940d5729a.jpg" /></p>

<b>HoME: a Household Multimodal Environment (2017)</b> [[Link]](https://home-platform.github.io/)
<br>HoME integrates over 45,000 diverse 3D house layouts based on the SUNCG dataset, a scale which may facilitate learning, generalization, and transfer. HoME is an open-source, OpenAI Gym-compatible platform extensible to tasks in reinforcement learning, language grounding, sound-based navigation, robotics, multi-agent learning.
<p align="center"><img width="50%" src="https://home-platform.github.io/assets/overview.png" /></p>

<b>AI2-THOR: Photorealistic Interactive Environments for AI Agents</b> [[Link]](http://ai2thor.allenai.org/)
<br>AI2-THOR is a photo-realistic interactable framework for AI agents. There are a total 120 scenes in version 1.0 of the THOR environment covering four different room categories: kitchens, living rooms, bedrooms, and bathrooms. Each room has a number of actionable objects.
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/AI2-Thor.jpeg" /></p>

<a name="single_classification" />

## Single Object Classification
:space_invader: <b>3D ShapeNets: A Deep Representation for Volumetric Shapes (2015)</b> [[Paper]](http://3dshapenets.cs.princeton.edu/)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/3ed23386284a5639cb3e8baaecf496caa766e335/1-Figure1-1.png" /></p>

:space_invader: <b>VoxNet: A 3D Convolutional Neural Network for Real-Time Object Recognition (2015)</b> [[Paper]](http://www.dimatura.net/publications/voxnet_maturana_scherer_iros15.pdf) [[Code]](https://github.com/dimatura/voxnet)
<p align="center"><img width="50%" src="http://www.dimatura.net/research/voxnet/car_voxnet_side.png" /></p>

:camera: <b>Multi-view Convolutional Neural Networks  for 3D Shape Recognition (2015)</b> [[Paper]](http://vis-www.cs.umass.edu/mvcnn/)
<p align="center"><img width="50%" src="http://vis-www.cs.umass.edu/mvcnn/images/mvcnn.png" /></p>

:camera: <b>DeepPano: Deep Panoramic Representation for 3-D Shape Recognition (2015)</b> [[Paper]](http://mclab.eic.hust.edu.cn/UpLoadFiles/Papers/DeepPano_SPL2015.pdf)
<p align="center"><img width="30%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/5a1b5d31905d8cece7b78510f51f3d8bbb063063/1-Figure3-1.png" /></p>

:space_invader::camera: <b>FusionNet: 3D Object Classification Using Multiple Data Representations (2016)</b> [[Paper]](https://stanford.edu/~rezab/papers/fusionnet.pdf)
<p align="center"><img width="30%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/0aab8fbcef1f0a14f5653d170ca36f4e5aae8010/6-Figure5-1.png" /></p>

:space_invader::camera: <b>Volumetric and Multi-View CNNs for Object Classification on 3D Data (2016)</b> [[Paper]](https://arxiv.org/pdf/1604.03265.pdf) [[Code]](https://github.com/charlesq34/3dcnn.torch)
<p align="center"><img width="40%" src="http://graphics.stanford.edu/projects/3dcnn/teaser.jpg" /></p>

:space_invader: <b>Generative and Discriminative Voxel Modeling with Convolutional Neural Networks (2016)</b> [[Paper]](https://arxiv.org/pdf/1608.04236.pdf) [[Code]](https://github.com/ajbrock/Generative-and-Discriminative-Voxel-Modeling)
<p align="center"><img width="50%" src="http://davidstutz.de/wordpress/wp-content/uploads/2017/02/brock_vae.png" /></p>

:space_invader: <b>3D GAN: Learning a Probabilistic Latent Space of Object Shapes via 3D Generative-Adversarial Modeling (2016)</b> [[Paper]](https://arxiv.org/pdf/1610.07584.pdf) [[Code]](https://github.com/zck119/3dgan-release)
<p align="center"><img width="50%" src="http://3dgan.csail.mit.edu/images/model.jpg" /></p>

:space_invader: <b>Generative and Discriminative Voxel Modeling with Convolutional Neural Networks (2017)</b> [[Paper]](https://github.com/ajbrock/Generative-and-Discriminative-Voxel-Modeling)
<p align="center"><img width="50%" src="https://github.com/ajbrock/Generative-and-Discriminative-Voxel-Modeling/blob/master/doc/GUI3.png" /></p>

:space_invader: <b>FPNN: Field Probing Neural Networks for 3D Data (2016)</b> [[Paper]](http://yangyanli.github.io/FPNN/) [[Code]](https://github.com/yangyanli/FPNN)
<p align="center"><img width="30%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/15ca7adccf5cd4dc309cdcaa6328f4c429ead337/1-Figure2-1.png" /></p>

:space_invader: <b>OctNet: Learning Deep 3D Representations at High Resolutions (2017)</b> [[Paper]](https://arxiv.org/pdf/1611.05009.pdf) [[Code]](https://github.com/griegler/octnet)
<p align="center"><img width="30%" src="https://is.tuebingen.mpg.de/uploads/publication/image/18921/img03.png" /></p>

:space_invader: <b>O-CNN: Octree-based Convolutional Neural Networks for 3D Shape Analysis (2017)</b> [[Paper]](http://wang-ps.github.io/O-CNN) [[Code]](https://github.com/Microsoft/O-CNN)
<p align="center"><img width="50%" src="http://wang-ps.github.io/O-CNN_files/teaser.png" /></p>

:space_invader: <b>Orientation-boosted voxel nets for 3D object recognition (2017)</b> [[Paper]](https://lmb.informatik.uni-freiburg.de/Publications/2017/SZB17a/) [[Code]](https://github.com/lmb-freiburg/orion)
<p align="center"><img width="50%" src="https://lmb.informatik.uni-freiburg.de/Publications/2017/SZB17a/teaser_w.png" /></p>

:game_die: <b>PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation (2017)</b> [[Paper]](http://stanford.edu/~rqi/pointnet/) [[Code]](https://github.com/charlesq34/pointnet)
<p align="center"><img width="40%" src="https://web.stanford.edu/~rqi/papers/pointnet.png" /></p>

:game_die: <b>PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space (2017)</b> [[Paper]](https://arxiv.org/pdf/1706.02413.pdf) [[Code]](https://github.com/charlesq34/pointnet2)
<p align="center"><img width="40%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/PointNet%2B%2B-%20Deep%20Hierarchical%20Feature%20Learning%20on%20Point%20Sets%20in%20a%20Metric%20Space.png" /></p>

:camera: <b>Feedback Networks (2017)</b> [[Paper]](http://feedbacknet.stanford.edu/) [[Code]](https://github.com/amir32002/feedback-networks)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Feedback%20Networks.png" /></p>

:game_die: <b>Escape from Cells: Deep Kd-Networks for The Recognition of 3D Point Cloud Models (2017)</b> [[Paper]](http://www.arxiv.org/pdf/1704.01222.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Escape From Cells.png" /></p>

<a name="multiple_detection" />

## Multiple Objects Detection
<b>Sliding Shapes for 3D Object Detection in Depth Images (2014)</b> [[Paper]](http://slidingshapes.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://slidingshapes.cs.princeton.edu/teaser.jpg" /></p>

<b>Object Detection in 3D Scenes Using CNNs in Multi-view Images (2016)</b> [[Paper]](https://stanford.edu/class/ee367/Winter2016/Qi_Report.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Object%20Detection%20in%203D%20Scenes%20Using%20CNNs%20in%20Multi-view%20Images.png" /></p>

<b>Deep Sliding Shapes for Amodal 3D Object Detection in RGB-D Images (2016)</b> [[Paper]](http://dss.cs.princeton.edu/) [[Code]](https://github.com/shurans/DeepSlidingShape)
<p align="center"><img width="50%" src="http://3dvision.princeton.edu/slide/DSS.jpg" /></p>

<b>DeepContext: Context-Encoding Neural Pathways  for 3D Holistic Scene Understanding (2016)</b> [[Paper]](http://deepcontext.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://deepcontext.cs.princeton.edu/teaser.png" /></p>

<b>SUN RGB-D: A RGB-D Scene Understanding Benchmark Suite (2017)</b> [[Paper]](http://rgbd.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://rgbd.cs.princeton.edu/teaser.jpg" /></p>

<b>VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection (2017)</b> [[Paper]](https://arxiv.org/pdf/1711.06396.pdf)
<p align="center"><img width="50%" src="https://pbs.twimg.com/media/DPMtLhHXUAcQUj2.jpg" /></p>

<b>Frustum PointNets for 3D Object Detection from RGB-D Data (2017)</b> [[Paper]](https://arxiv.org/pdf/1711.08488.pdf)
<p align="center"><img width="50%" src="https://arxiv-sanity-sanity-production.s3.amazonaws.com/render-output/17548/fig/teaser.svg" /></p>

<a name="segmentation" />

## Scene/Object Semantic Segmentation
<b>Learning 3D Mesh Segmentation and Labeling (2010)</b> [[Paper]](https://people.cs.umass.edu/~kalo/papers/LabelMeshes/LabelMeshes.pdf)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/0bf390e2a14f74bcc8838d5fb1c0c4cc60e92eb7/7-Figure7-1.png" /></p>

<b>Unsupervised Co-Segmentation of a Set of Shapes via Descriptor-Space Spectral Clustering (2011)</b> [[Paper]](https://www.cs.sfu.ca/~haoz/pubs/sidi_siga11_coseg.pdf)
<p align="center"><img width="30%" src="http://people.scs.carleton.ca/~olivervankaick/cosegmentation/results6.png" /></p>

<b>Single-View Reconstruction via Joint Analysis of Image and Shape Collections (2015)</b> [[Paper]](https://www.cs.utexas.edu/~huangqx/modeling_sig15.pdf) [[Code]](https://github.com/huangqx/image_shape_align)
<p align="center"><img width="50%" src="http://vladlen.info/wp-content/uploads/2015/05/single-view.png" /></p>

<b>3D Shape Segmentation with Projective Convolutional Networks (2017)</b> [[Paper]](http://people.cs.umass.edu/~kalo/papers/shapepfcn/) [[Code]](https://github.com/kalov/ShapePFCN)
<p align="center"><img width="50%" src="http://people.cs.umass.edu/~kalo/papers/shapepfcn/teaser.jpg" /></p>

<b>Learning Hierarchical Shape Segmentation and Labeling from Online Repositories (2017)</b> [[Paper]](http://cs.stanford.edu/~ericyi/project_page/hier_seg/index.html)
<p align="center"><img width="50%" src="http://cs.stanford.edu/~ericyi/project_page/hier_seg/figures/teaser.jpg" /></p>

:game_die: <b>PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation (2017)</b> [[Paper]](http://stanford.edu/~rqi/pointnet/) [[Code]](https://github.com/charlesq34/pointnet)
<p align="center"><img width="40%" src="https://web.stanford.edu/~rqi/papers/pointnet.png" /></p>

:game_die: <b>PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space (2017)</b> [[Paper]](https://arxiv.org/pdf/1706.02413.pdf) [[Code]](https://github.com/charlesq34/pointnet2)
<p align="center"><img width="40%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/PointNet%2B%2B-%20Deep%20Hierarchical%20Feature%20Learning%20on%20Point%20Sets%20in%20a%20Metric%20Space.png" /></p>

:game_die: <b>3D Graph Neural Networks for RGBD Semantic Segmentation (2017)</b> [[Paper]](http://www.cs.toronto.edu/~rjliao/papers/iccv_2017_3DGNN.pdf)
<p align="center"><img width="40%" src="http://www.fonow.com/Images/2017-10-18/66372-20171018115809740-2125227250.jpg" /></p>

:game_die: <b>3DCNN-DQN-RNN: A Deep Reinforcement Learning Framework for Semantic
Parsing of Large-scale 3D Point Clouds (2017)</b> [[Paper]](https://arxiv.org/pdf/1707.06783.pdf)
<p align="center"><img width="40%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/3DCNN-DQN-RNN.png" /></p>

:game_die::space_invader: <b>Semantic Segmentation of Indoor Point Clouds using Convolutional Neural Networks (2017)</b> [[Paper]](https://www.isprs-ann-photogramm-remote-sens-spatial-inf-sci.net/IV-4-W4/101/2017/isprs-annals-IV-4-W4-101-2017.pdf)
<p align="center"><img width="55%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Semantic Segmentation of Indoor Point Clouds using Convolutional Neural Networks.png" /></p>

:game_die::space_invader: <b>SEGCloud: Semantic Segmentation of 3D Point Clouds (2017)</b> [[Paper]](https://arxiv.org/pdf/1710.07563.pdf)
<p align="center"><img width="55%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/SEGCloud.png" /></p>

:game_die::space_invader: <b>Large-Scale 3D Shape Reconstruction and Segmentation from ShapeNet Core55 (2017)</b> [[Paper]](https://arxiv.org/pdf/1710.06104.pdf)
<p align="center"><img width="40%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Core55.png" /></p>

<a name="3d_synthesis" />

## 3D Synthesis/Reconstruction

<a name="3d_synthesis_model_based" />

_Parametric Morphable Model-based methods_

<b>A Morphable Model For The Synthesis Of 3D Faces (1999)</b> [[Paper]](http://gravis.dmi.unibas.ch/publications/Sigg99/morphmod2.pdf)[[Code]](https://github.com/MichaelMure/3DMM)
<p align="center"><img width="40%" src="http://mblogthumb3.phinf.naver.net/MjAxNzAzMTdfMjcz/MDAxNDg5NzE3MzU0ODI3.9lQioLxwoGmtoIVXX9sbVOzhezoqgKMKiTovBnbUFN0g.sXN5tG4Kohgk7OJEtPnux-mv7OAoXVxxCyo3SGZMc6Yg.PNG.atelierjpro/031717_0222_DataDrivenS4.png?type=w420" /></p>

<b>The Space of Human Body Shapes: Reconstruction and Parameterization from Range Scans (2003)</b> [[Paper]](http://grail.cs.washington.edu/projects/digital-human/pub/allen03space-submit.pdf)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/46d39b0e21ae956e4bcb7a789f92be480d45ee12/7-Figure10-1.png" /></p>

<a name="3d_synthesis_template_based" />

_Part-based Template Learning methods_

<b>Modeling by Example (2004)</b> [[Paper]](http://www.cs.princeton.edu/~funk/sig04a.pdf)
<p align="center"><img width="20%" src="http://gfx.cs.princeton.edu/pubs/Funkhouser_2004_MBE/chair.jpg" /></p>

<b>Model Composition from Interchangeable Components (2007)</b> [[Paper]](http://www.cs.princeton.edu/courses/archive/spring11/cos598A/pdfs/Kraevoy07.pdf)
<p align="center"><img width="40%" src="http://www.cs.ubc.ca/labs/imager/tr/2007/Vlad_Shuffler/teaser.jpg" /></p>

<b>Data-Driven Suggestions for Creativity Support in 3D Modeling (2010)</b> [[Paper]](http://vladlen.info/publications/data-driven-suggestions-for-creativity-support-in-3d-modeling/)
<p align="center"><img width="50%" src="http://vladlen.info/wp-content/uploads/2011/12/creativity.png" /></p>

<b>Photo-Inspired Model-Driven 3D Object Modeling (2011)</b> [[Paper]](http://kevinkaixu.net/projects/photo-inspired.html)
<p align="center"><img width="50%" src="http://kevinkaixu.net/projects/photo-inspired/overview.PNG" /></p>

<b>Probabilistic Reasoning for Assembly-Based 3D Modeling (2011)</b> [[Paper]](https://people.cs.umass.edu/~kalo/papers/assembly/ProbReasoningShapeModeling.pdf)
<p align="center"><img width="50%" src="http://vladlen.info/wp-content/uploads/2011/12/highlight9.png" /></p>

<b>A Probabilistic Model for Component-Based Shape Synthesis (2012)</b> [[Paper]](https://people.cs.umass.edu/~kalo/papers/ShapeSynthesis/ShapeSynthesis.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/test1/blob/master/imgs/A%20Probabilistic%20Model%20for%20Component-Based%20Shape%20Synthesis.png" /></p>

<b>Structure Recovery by Part Assembly (2012)</b> [[Paper]](http://cg.cs.tsinghua.edu.cn/StructureRecovery/)
<p align="center"><img width="50%" src="https://github.com/timzhang642/test1/blob/master/imgs/Structure%20Recovery%20by%20Part%20Assembly.png" /></p>

<b>Fit and Diverse: Set Evolution for Inspiring 3D Shape Galleries (2012)</b> [[Paper]](http://kevinkaixu.net/projects/civil.html)
<p align="center"><img width="50%" src="http://kevinkaixu.net/projects/civil/teaser.png" /></p>

<b>AttribIt: Content Creation with Semantic Attributes (2013)</b> [[Paper]](https://people.cs.umass.edu/~kalo/papers/attribit/AttribIt.pdf)
<p align="center"><img width="30%" src="http://gfx.cs.princeton.edu/gfx/pubs/Chaudhuri_2013_ACC/teaser.jpg" /></p>

<b>Learning Part-based Templates from Large Collections of 3D Shapes (2013)</b> [[Paper]](http://shape.cs.princeton.edu/vkcorrs/papers/13_SIGGRAPH_CorrsTmplt.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/test1/blob/master/imgs/Learning%20Part-based%20Templates%20from%20Large%20Collections%20of%203D%20Shapes.png" /></p>

<b>Topology-Varying 3D Shape Creation via Structural Blending (2014)</b> [[Paper]](http://gruvi.cs.sfu.ca/project/topo/)
<p align="center"><img width="50%" src="https://i.ytimg.com/vi/Xc4qf7v6a-w/maxresdefault.jpg" /></p>

<b>Estimating Image Depth using Shape Collections (2014)</b> [[Paper]](http://vecg.cs.ucl.ac.uk/Projects/SmartGeometry/image_shape_net/imageShapeNet_sigg14.html)
<p align="center"><img width="50%" src="http://vecg.cs.ucl.ac.uk/Projects/SmartGeometry/image_shape_net/paper_docs/pipeline.jpg" /></p>

<b>Single-View Reconstruction via Joint Analysis of Image and Shape Collections (2015)</b> [[Paper]](https://www.cs.utexas.edu/~huangqx/modeling_sig15.pdf)
<p align="center"><img width="50%" src="http://vladlen.info/wp-content/uploads/2015/05/single-view.png" /></p>

<b>Interchangeable Components for Hands-On Assembly Based Modeling (2016)</b> [[Paper]](http://www.cs.umb.edu/~craigyu/papers/handson_low_res.pdf)
<p align="center"><img width="30%" src="https://github.com/timzhang642/test1/blob/master/imgs/Interchangeable%20Components%20for%20Hands-On%20Assembly%20Based%20Modeling.png" /></p>

<b>Shape Completion from a Single RGBD Image (2016)</b> [[Paper]](http://www.kunzhou.net/2016/shapecompletion-tvcg16.pdf)
<p align="center"><img width="40%" src="http://tianjiashao.com/Images/2015/completion.jpg" /></p>

<a name="3d_synthesis_dl_based" />

_Deep Learning Methods_

:camera: <b>Learning to Generate Chairs, Tables and Cars with Convolutional Networks (2014)</b> [[Paper]](https://arxiv.org/pdf/1411.5928.pdf)
<p align="center"><img width="50%" src="https://zo7.github.io/img/2016-09-25-generating-faces/chairs-model.png" /></p>

:camera: <b>Weakly-supervised Disentangling with Recurrent Transformations for 3D View Synthesis (2015, NIPS)</b> [[Paper]](https://papers.nips.cc/paper/5639-weakly-supervised-disentangling-with-recurrent-transformations-for-3d-view-synthesis.pdf)
<p align="center"><img width="50%" src="https://github.com/jimeiyang/deepRotator/blob/master/demo_img.png" /></p>

:game_die: <b>Analysis and synthesis of 3D shape families via deep-learned generative models of surfaces (2015)</b> [[Paper]](https://people.cs.umass.edu/~hbhuang/publications/bsm/)
<p align="center"><img width="50%" src="https://people.cs.umass.edu/~hbhuang/publications/bsm/bsm_teaser.jpg" /></p>

:camera: <b>Weakly-supervised Disentangling with Recurrent Transformations for 3D View Synthesis (2015)</b> [[Paper]](https://papers.nips.cc/paper/5639-weakly-supervised-disentangling-with-recurrent-transformations-for-3d-view-synthesis.pdf) [[Code]](https://github.com/jimeiyang/deepRotator)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/042993c46294a542946c9c1706b7b22deb1d7c43/2-Figure1-1.png" /></p>

:camera: <b>Multi-view 3D Models from Single Images with a Convolutional Network (2016)</b> [[Paper]](https://arxiv.org/pdf/1511.06702.pdf) [[Code]](https://github.com/lmb-freiburg/mv3d)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/3d7ca5ad34f23a5fab16e73e287d1a059dc7ef9a/4-Figure2-1.png" /></p>

:camera: <b>View Synthesis by Appearance Flow (2016)</b> [[Paper]](https://people.eecs.berkeley.edu/~tinghuiz/papers/eccv16_appflow.pdf) [[Code]](https://github.com/tinghuiz/appearance-flow)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/12280506dc8b5c3ca2db29fc3be694d9a8bef48c/6-Figure2-1.png" /></p>

:space_invader: <b>Voxlets: Structured Prediction of Unobserved Voxels From a Single Depth Image (2016)</b> [[Paper]](http://visual.cs.ucl.ac.uk/pubs/depthPrediction/http://visual.cs.ucl.ac.uk/pubs/depthPrediction/) [[Code]](https://github.com/mdfirman/voxlets)
<p align="center"><img width="30%" src="https://i.ytimg.com/vi/1wy4y2GWD5o/maxresdefault.jpg" /></p>

:space_invader: <b>3D-R2N2: 3D Recurrent Reconstruction Neural Network (2016)</b> [[Paper]](http://cvgl.stanford.edu/3d-r2n2/) [[Code]](https://github.com/chrischoy/3D-R2N2)
<p align="center"><img width="50%" src="http://3d-r2n2.stanford.edu/imgs/overview.png" /></p>

:space_invader: <b>Perspective Transformer Nets: Learning Single-View 3D Object Reconstruction without 3D Supervision (2016)</b> [[Paper]](https://eng.ucmerced.edu/people/jyang44/papers/nips16_ptn.pdf)
<p align="center"><img width="70%" src="https://sites.google.com/site/skywalkeryxc/_/rsrc/1481104596238/perspective_transformer_nets/network_arch.png" /></p>

:space_invader: <b>TL-Embedding Network: Learning a Predictable and Generative Vector Representation for Objects (2016)</b> [[Paper]](https://arxiv.org/pdf/1603.08637.pdf)
<p align="center"><img width="50%" src="https://rohitgirdhar.github.io/GenerativePredictableVoxels/assets/webteaser.jpg" /></p>

:space_invader: <b>3D GAN: Learning a Probabilistic Latent Space of Object Shapes via 3D Generative-Adversarial Modeling (2016)</b> [[Paper]](https://arxiv.org/pdf/1610.07584.pdf)
<p align="center"><img width="50%" src="http://3dgan.csail.mit.edu/images/model.jpg" /></p>

:space_invader: <b>3D Shape Induction from 2D Views of Multiple Objects (2016)</b> [[Paper]](https://arxiv.org/pdf/1612.05872.pdf)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/e78572eeef8b967dec420013c65a6684487c13b2/2-Figure2-1.png" /></p>

:camera: <b>Unsupervised Learning of 3D Structure from Images (2016)</b> [[Paper]](https://arxiv.org/pdf/1607.00662.pdf)
<p align="center"><img width="50%" src="https://adriancolyer.files.wordpress.com/2016/12/unsupervised-3d-fig-10.jpeg?w=600" /></p>

:space_invader: <b>Generative and Discriminative Voxel Modeling with Convolutional Neural Networks (2016)</b> [[Paper]](https://arxiv.org/pdf/1608.04236.pdf) [[Code]](https://github.com/ajbrock/Generative-and-Discriminative-Voxel-Modeling)
<p align="center"><img width="50%" src="http://davidstutz.de/wordpress/wp-content/uploads/2017/02/brock_vae.png" /></p>

:camera: <b>Multi-view Supervision for Single-view Reconstruction via Differentiable Ray Consistency (2017)</b> [[Paper]](https://shubhtuls.github.io/drc/)
<p align="center"><img width="50%" src="https://shubhtuls.github.io/drc/resources/images/teaserChair.png" /></p>

:camera: <b>Synthesizing 3D Shapes via Modeling Multi-View Depth Maps and Silhouettes with Deep Generative Networks (2017)</b> [[Paper]](http://openaccess.thecvf.com/content_cvpr_2017/papers/Soltani_Synthesizing_3D_Shapes_CVPR_2017_paper.pdf)  [[Code]](https://github.com/Amir-Arsalan/Synthesize3DviaDepthOrSil)
<p align="center"><img width="50%" src="https://jiajunwu.com/images/spotlight_3dvae.jpg" /></p>

:space_invader: <b>Octree Generating Networks: Efficient Convolutional Architectures for High-resolution 3D Outputs (2017)</b> [[Paper]](https://arxiv.org/pdf/1703.09438.pdf) [[Code]](https://github.com/lmb-freiburg/ogn)
<p align="center"><img width="50%" src="https://ai2-s2-public.s3.amazonaws.com/figures/2016-11-08/6c2a292bb018a8742cbb0bbc5e23dd0a454ffe3a/2-Figure2-1.png" /></p>

:space_invader: <b>Hierarchical Surface Prediction for 3D Object Reconstruction (2017)</b> [[Paper]](https://arxiv.org/pdf/1704.00710.pdf)
<p align="center"><img width="50%" src="http://bair.berkeley.edu/blog/assets/hsp/image_2.png" /></p>

:space_invader: <b>OctNetFusion: Learning Depth Fusion from Data (2017)</b> [[Paper]](https://arxiv.org/pdf/1704.01047.pdf) [[Code]](https://github.com/griegler/octnetfusion)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/OctNetFusion-%20Learning%20Depth%20Fusion%20from%20Data.jpeg" /></p>

:game_die: <b>A Point Set Generation Network for 3D Object Reconstruction from a Single Image (2017)</b> [[Paper]](http://ai.stanford.edu/~haosu/papers/SI2PC_arxiv_submit.pdf) [[Code]](https://github.com/fanhqme/PointSetGeneration)
<p align="center"><img width="50%" src="http://gting.me/2017/07/17/pr-point-set-generation-from-single-image/ps3d_introduction.PNG" /></p>

:game_die: <b>Learning Representations and Generative Models for 3D Point Clouds (2017)</b> [[Paper]](https://arxiv.org/pdf/1707.02392.pdf) [[Code]](https://github.com/optas/latent_3d_points)
<p align="center"><img width="50%" src="https://github.com/optas/latent_3d_points/blob/master/doc/images/teaser.jpg" /></p>

:game_die: <b>Shape Generation using Spatially Partitioned Point Clouds (2017)</b> [[Paper]](https://arxiv.org/pdf/1707.06267.pdf)
<p align="center"><img width="50%" src="http://mgadelha.me/sppc/fig/abstract.png" /></p>

:game_die: <b>PCPNET Learning Local Shape Properties from Raw Point Clouds (2017)</b> [[Paper]](https://arxiv.org/pdf/1710.04954.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/PCPNET%20Learning%20Local%20Shape%20Properties%20from%20Raw%20Point%20Clouds%20(2017).jpeg" /></p>

:game_die: <b>DeformNet: Free-Form Deformation Network for 3D Shape Reconstruction from a Single Image (2017)</b> [[Paper]](http://ai.stanford.edu/~haosu/papers/SI2PC_arxiv_submit.pdf)
<p align="center"><img width="50%" src="https://chrischoy.github.io/images/publication/deformnet/model.png" /></p>

:camera: <b>Transformation-Grounded Image Generation Network for Novel 3D View Synthesis (2017)</b> [[Paper]](http://www.cs.unc.edu/~eunbyung/tvsn/) [[Code]](https://github.com/silverbottlep/tvsn)
<p align="center"><img width="50%" src="https://eng.ucmerced.edu/people/jyang44/pics/view_synthesis.gif" /></p>

:camera: <b>Tag Disentangled Generative Adversarial Networks for Object Image Re-rendering (2017)</b> [[Paper]](http://static.ijcai.org/proceedings-2017/0404.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Tag%20Disentangled%20Generative%20Adversarial%20Networks%20for%20Object%20Image%20Re-rendering.jpeg" /></p>

:camera: <b>3D Shape Reconstruction from Sketches via Multi-view Convolutional Networks (2017)</b> [[Paper]](http://www.cs.unc.edu/~eunbyung/tvsn/) [[Code]](https://github.com/happylun/SketchModeling)
<p align="center"><img width="50%" src="https://people.cs.umass.edu/~zlun/papers/SketchModeling/SketchModeling_teaser.png" /></p>

:space_invader: <b>Interactive 3D Modeling with a Generative Adversarial Network (2017)</b> [[Paper]](https://arxiv.org/pdf/1706.05170.pdf)
<p align="center"><img width="50%" src="https://pbs.twimg.com/media/DCsPKLqXoAEBd-V.jpg" /></p>

:camera::space_invader: <b>Weakly supervised 3D Reconstruction with Adversarial Constraint (2017)</b> [[Paper]](https://arxiv.org/pdf/1705.10904.pdf) [[Code]](https://github.com/jgwak/McRecon)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Weakly%20supervised%203D%20Reconstruction%20with%20Adversarial%20Constraint%20(2017).jpeg" /></p>

:gem: <b>Exploring Generative 3D Shapes Using Autoencoder Networks (Autodesk 2017)</b> [[Paper]](https://www.autodeskresearch.com/publications/exploring_generative_3d_shapes)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Exploring%20Generative%203D%20Shapes%20Using%20Autoencoder%20Networks.jpeg" /></p>

:pill: <b>GRASS: Generative Recursive Autoencoders for Shape Structures (SIGGRAPH 2017)</b> [[Paper]](http://kevinkaixu.net/projects/grass.html) [[Code]](https://github.com/junli-lj/grass) [[code]](https://github.com/kevin-kaixu/grass_pytorch)
<p align="center"><img width="50%" src="http://kevinkaixu.net/projects/grass/teaser.jpg" /></p>

:gem: <b>Mesh-based Autoencoders for Localized Deformation Component Analysis (2017)</b> [[Paper]](https://arxiv.org/pdf/1709.04304.pdf)
<p align="center"><img width="50%" src="http://qytan.com/img/point_conv.jpg" /></p>

:gem: <b>Neural 3D Mesh Renderer (2017)</b> [[Paper]](http://hiroharu-kato.com/projects_en/neural_renderer.html) [[Code]](https://github.com/hiroharu-kato/neural_renderer.git)
<p align="center"><img width="50%" src="https://pbs.twimg.com/media/DPSm-4HWkAApEZd.jpg" /></p>

:game_die::space_invader: <b>Large-Scale 3D Shape Reconstruction and Segmentation from ShapeNet Core55 (2017)</b> [[Paper]](https://arxiv.org/pdf/1710.06104.pdf)
<p align="center"><img width="40%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Core55.png" /></p>

:space_invader: <b>Pix2vox: Sketch-Based 3D Exploration with Stacked Generative Adversarial Networks (2017)</b> [[Code]](https://github.com/maxorange/pix2vox)
<p align="center"><img width="50%" src="https://github.com/maxorange/pix2vox/blob/master/img/sample.gif" /></p>

:camera::space_invader: <b>What You Sketch Is What You Get: 3D Sketching using Multi-View Deep Volumetric Prediction (2017)</b> [[Paper]](https://arxiv.org/pdf/1707.08390.pdf)
<p align="center"><img width="50%" src="https://arxiv-sanity-sanity-production.s3.amazonaws.com/render-output/31631/x1.png" /></p>

<a name="style_transfer" />

## Style Transfer
<b>Style-Content Separation by Anisotropic Part Scales (2010)</b> [[Paper]](https://www.cs.sfu.ca/~haoz/pubs/xu_siga10_style.pdf)
<p align="center"><img width="50%" src="https://sites.google.com/site/kevinkaixu/_/rsrc/1472852123106/publications/style_b.jpg?height=145&width=400" /></p>

<b>Design Preserving Garment Transfer (2012)</b> [[Paper]](https://hal.inria.fr/hal-00695903/file/GarmentTransfer.pdf)
<p align="center"><img width="30%" src="https://hal.inria.fr/hal-00695903v2/file/02_WomanToAll.jpg" /></p>

<b>Analogy-Driven 3D Style Transfer (2014)</b> [[Paper]](http://www.chongyangma.com/publications/st/index.html)
<p align="center"><img width="50%" src="http://www.cs.ubc.ca/~chyma/publications/st/2014_st_teaser.png" /></p>

<b>Elements of Style: Learning Perceptual Shape Style Similarity (2015)</b> [[Paper]](http://people.cs.umass.edu/~zlun/papers/StyleSimilarity/StyleSimilarity.pdf) [[Code]](https://github.com/happylun/StyleSimilarity)
<p align="center"><img width="50%" src="https://people.cs.umass.edu/~zlun/papers/StyleSimilarity/StyleSimilarity_teaser.jpg" /></p>

<b>Functionality Preserving Shape Style Transfer (2016)</b> [[Paper]](http://people.cs.umass.edu/~zlun/papers/StyleTransfer/StyleTransfer.pdf) [[Code]](https://github.com/happylun/StyleTransfer)
<p align="center"><img width="50%" src="https://people.cs.umass.edu/~zlun/papers/StyleTransfer/StyleTransfer_teaser.jpg" /></p>

<b>Unsupervised Texture Transfer from Images to Model Collections (2016)</b> [[Paper]](http://ai.stanford.edu/~haosu/papers/siga16_texture_transfer_small.pdf)
<p align="center"><img width="50%" src="http://geometry.cs.ucl.ac.uk/projects/2016/texture_transfer/paper_docs/teaser.png" /></p>

<b>Learning Detail Transfer based on Geometric Features (2017)</b> [[Paper]](http://surfacedetails.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://surfacedetails.cs.princeton.edu/images/teaser.png" /></p>

<b>Neural 3D Mesh Renderer (2017)</b> [[Paper]](http://hiroharu-kato.com/projects_en/neural_renderer.html) [[Code]](https://github.com/hiroharu-kato/neural_renderer.git)
<p align="center"><img width="50%" src="https://pbs.twimg.com/media/DPSm-4HWkAApEZd.jpg" /></p>

<a name="scene_synthesis" />

## Scene Synthesis
<b>Make It Home: Automatic Optimization of Furniture Arrangement (2011, SIGGRAPH)</b> [[Paper]](http://people.sutd.edu.sg/~saikit/projects/furniture/index.html)
<p align="center"><img width="40%" src="https://www.cs.umb.edu/~craigyu/img/papers/furniture.gif" /></p>

<b>Interactive Furniture Layout Using Interior Design Guidelines (2011)</b> [[Paper]](http://graphics.stanford.edu/~pmerrell/furnitureLayout.htm)
<p align="center"><img width="50%" src="http://vis.berkeley.edu/papers/furnitureLayout/furnitureBig.jpg" /></p>

<b>Synthesizing Open Worlds with Constraints using Locally Annealed Reversible Jump MCMC (2012)</b> [[Paper]](http://graphics.stanford.edu/~lfyg/owl.pdf)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/Synthesizing%20Open%20Worlds%20with%20Constraints%20using%20Locally%20Annealed%20Reversible%20Jump%20MCMC%20(2012).jpeg" /></p>

<b>Sketch2Scene: Sketch-based Co-retrieval  and Co-placement of 3D Models  (2013)</b> [[Paper]](http://sweb.cityu.edu.hk/hongbofu/projects/sketch2scene_sig13/#.WWWge__ysb0)
<p align="center"><img width="40%" src="http://sunweilun.github.io/images/paper/sketch2scene_thumb.jpg" /></p>

<b>Action-Driven 3D Indoor Scene Evolution (2016)</b> [[Paper]](https://www.cs.sfu.ca/~haoz/pubs/ma_siga16_action.pdf)
<p align="center"><img width="50%" src="https://maruitx.github.io/project/adise/teaser.jpg" /></p>

<b>Relationship Templates for Creating Scene Variations (2016)</b> [[Paper]](http://geometry.cs.ucl.ac.uk/projects/2016/relationship-templates/)
<p align="center"><img width="50%" src="http://geometry.cs.ucl.ac.uk/projects/2016/relationship-templates/paper_docs/teaser.png" /></p>

<b>IM2CAD (2017)</b> [[Paper]](http://homes.cs.washington.edu/~izadinia/im2cad.html)
<p align="center"><img width="50%" src="http://i.imgur.com/KhtOeuB.jpg" /></p>

<b>Raster-to-Vector: Revisiting Floorplan Transformation (2017, ICCV)</b> [[Paper]](http://www.cse.wustl.edu/~chenliu/floorplan-transformation.html) [[Code]](https://github.com/art-programmer/FloorplanTransformation)
<p align="center"><img width="50%" src="https://www.cse.wustl.edu/~chenliu/floorplan-transformation/teaser.png" /></p>

<a name="scene_understanding" />

## Scene Understanding
<b>Understanding Indoor Scenes Using 3D Geometric Phrases (2013)</b> [[Paper]](http://cvgl.stanford.edu/projects/3dgp/)
<p align="center"><img width="30%" src="http://cvgl.stanford.edu/projects/3dgp/images/title.png" /></p>

<b>SceneGrok: Inferring Action Maps in 3D Environments (2014, SIGGRAPH)</b> [[Paper]](http://graphics.stanford.edu/projects/scenegrok/)
<p align="center"><img width="50%" src="http://graphics.stanford.edu/projects/scenegrok/scenegrok.png" /></p>

<b>PanoContext: A Whole-room 3D Context Model for Panoramic Scene Understanding (2014)</b> [[Paper]](http://panocontext.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://panocontext.cs.princeton.edu/teaser.jpg" /></p>

<b>Learning Informative Edge Maps for Indoor Scene Layout Prediction (2015)</b> [[Paper]](http://web.engr.illinois.edu/~slazebni/publications/iccv15_informative.pdf)
<p align="center"><img width="50%" src="http://img.blog.csdn.net/20170820185439268?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvYmFpeXU5ODIxMTc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast" /></p>

<b>Rent3D: Floor-Plan Priors for Monocular Layout Estimation (2015)</b> [[Paper]](http://www.cs.toronto.edu/~fidler/projects/rent3D.html)
<p align="center"><img width="50%" src="http://www.cs.toronto.edu/~fidler/projects/layout-res.jpg" /></p>

<b>A Coarse-to-Fine Indoor Layout Estimation (CFILE) Method (2016)</b> [[Paper]](https://pdfs.semanticscholar.org/7024/a92186b81e6133dc779f497d06877b48d82b.pdf?_ga=2.54181869.497995160.1510977308-665742395.1510465328)
<p align="center"><img width="50%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/A%20Coarse-to-Fine%20Indoor%20Layout%20Estimation%20(CFILE)%20Method%20(2016).png" /></p>

<b>DeLay: Robust Spatial Layout Estimation for Cluttered Indoor Scenes (2016)</b> [[Paper]](http://deeplayout.stanford.edu/)
<p align="center"><img width="30%" src="https://github.com/timzhang642/3D-Machine-Learning/blob/master/imgs/DeLay-Robust%20Spatial%20Layout%20Estimation%20for%20Cluttered%20Indoor%20Scenes.png" /></p>

<b>3D Semantic Parsing of Large-Scale Indoor Spaces (2016)</b> [[Paper]](http://buildingparser.stanford.edu/method.html) [[Code]](https://github.com/alexsax/2D-3D-Semantics)
<p align="center"><img width="50%" src="http://buildingparser.stanford.edu/images/teaser.png" /></p>

<b>Single Image 3D Interpreter Network (2016)</b> [[Paper]](http://3dinterpreter.csail.mit.edu/) [[Code]](https://github.com/jiajunwu/3dinn)
<p align="center"><img width="50%" src="http://3dinterpreter.csail.mit.edu/images/spotlight_3dinn_large.jpg" /></p>

<b>Deep Multi-Modal Image Correspondence Learning (2016)</b> [[Paper]](http://www.cse.wustl.edu/~chenliu/floorplan-matching.html)
<p align="center"><img width="50%" src="https://www.cse.wustl.edu/~furukawa/carousel/2016-floorplan-wide.png" /></p>

<b>Physically-Based Rendering for Indoor Scene Understanding Using Convolutional Neural Networks (2017)</b> [[Paper]](http://3dvision.princeton.edu/projects/2016/PBRS/) [[Code]](https://github.com/yindaz/pbrs) [[Code]](https://github.com/yindaz/surface_normal) [[Code]](https://github.com/fyu/dilation) [[Code]](https://github.com/s9xie/hed)
<p align="center"><img width="50%" src="http://robots.princeton.edu/projects/2016/PBRS/teaser.jpg" /></p>

<b>RoomNet: End-to-End Room Layout Estimation (2017)</b> [[Paper]](https://arxiv.org/pdf/1703.06241.pdf)
<p align="center"><img width="50%" src="https://pbs.twimg.com/media/C7Z29GsV0AASEvR.jpg" /></p>

<b>SUN RGB-D: A RGB-D Scene Understanding Benchmark Suite (2017)</b> [[Paper]](http://rgbd.cs.princeton.edu/)
<p align="center"><img width="50%" src="http://rgbd.cs.princeton.edu/teaser.jpg" /></p>

<b>Semantic Scene Completion from a Single Depth Image (2017)</b> [[Paper]](http://sscnet.cs.princeton.edu/) [[Code]](https://github.com/shurans/sscnet)
<p align="center"><img width="50%" src="http://sscnet.cs.princeton.edu/teaser.jpg" /></p>
