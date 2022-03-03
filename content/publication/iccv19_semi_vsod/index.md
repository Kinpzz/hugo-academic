---
title: "Semi-Supervised Video Salient Object Detection Using Pseudo-Labels"
authors:
- yanpx
- Guanbin Li
- Yuan Xie
- Zhen Li 
- Chuan Wang
- Tianshui Chen
- Liang Lin
date: "2021-05-27T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2019-12-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: The 2019 IEEE International Conference on Computer Vision
publication_short: In *ICCV2019*

abstract: Deep learning-based video salient object detection has recently achieved great success with its performance significantly outperforming any other unsupervised methods. However, existing data-driven approaches heavily rely on a large quantity of pixel-wise annotated video frames to deliver such promising results. In this paper, we address the semi-supervised video salient object detection task using pseudo-labels. Specifically, we present an effective video saliency detector that consists of a spatial refinement network and a spatiotemporal module. Based on the same refinement network and motion information in terms of optical flow, we further propose a novel method for generating pixel-level pseudo-labels from sparsely annotated frames. By utilizing the generated pseudo-labels together with a part of manual annotations, our video saliency detector learns spatial and temporal cues for both contrast inference and coherence enhancement, thus producing accurate saliency maps. Experimental results demonstrate that our proposed semi-supervised method even greatly outperforms all the state-of-the-art fully supervised methods across three public benchmarks of VOS, DAVIS, and FBMS.

# Summary. An optional shortened abstract.
summary: The IEEE International Conference on Computer Vision **(ICCV)**, 2019. **[CCF A]**

tags:
- Deep Learning
- Salient Object Detection
- Video Object Segmentation
featured: true

links:
- name: CVF Open Access
  url: http://openaccess.thecvf.com/content_ICCV_2019/html/Yan_Semi-Supervised_Video_Salient_Object_Detection_Using_Pseudo-Labels_ICCV_2019_paper.html
url_pdf: 'https://arxiv.org/abs/1908.04051'
url_code: 'https://github.com/Kinpzz/RCRNet-Pytorch'
#url_dataset: '#'
#url_poster: '#'
#url_project: '/publication/iccv19_semi_vsod'
#url_slides: ''
#url_source: '#'
#url_video: '#'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'DAVIS: motorcross-jump'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

## Motivation

- Existing data-driven approaches of video salient object detection heavily rely on a large quantity of densely annotated video frames to deliver promising results.
- Consecutive video frames share small differences but will take a lot of efforts to densely annotate them and the labeling consistency is also hard to guarantee. 

## Contributions

- We propose a refinement network (RCRNet) equipped with a nonlocally enhanced recurrent (NER) module for spatiotemporal coherence modeling. 
- We propose a flow-guided pseudo-label generator (FGPLG) to generate pseudo-labels of intervals based on sparse annotations.
- As shown in Figure. 1, our model can produce reasonable and consistent pseudo-labels, which can even improve the boundary details (Example a) and overcome the labeling ambiguity between frames (Example b).

{{< figure src="pseudo_label_example.png" title="An example of pseudo labels" lightbox="true" width="500px" >}}

- Experimental results show that utilizing the joint supervision of pseudo-labels and sparse annotations can further improve the model performance. 



## Architecture

### RCRNet

{{< figure src="static_model.png" title="static model" lightbox="true"  width="400px">}}

### RCRNet+NER

![video_model](video_model.png)

### Flow-Guided Pseudo-Label Generator

![pseudo_label_generator](pseudo_label_generator.png)

## Results

### Quantitative Comparison

![comp_video_sota](comp_video_sota.png)

## Downloads

- Pre-computed  saliency maps the validation set of DAVIS2016, the test set of FBMS, and the test set of VOS. [[Google Drive](https://drive.google.com/open?id=1feY3GdNBS-LUBt0UDWwpA3fl9yHI4Vxr)] [[Baidu Pan](https://pan.baidu.com/s/1oXBr9qxyF-8vvilvV5kcPg) (passwd: u079)]

## Q&A

**Q1:** What is the difference between the semi-supervised strategies mentioned in semi-supervised video salient object detection (VSOD) and semi-supervised video object segmentation (VOS)?

**A1:** VOS can be categories into **semi-supervised** and **unsupervised** methods when referring to different **testing** schemes. Semi-supervised VOS will provide the annotation of the first frame when testing. Video salient object detection (VSOD) is more similar to unsupervised VOS as both of them do not resort to labeled frames during testing. Here, our proposed method use only a part of labeled frames for **training** and that makes we call it a semi-supervised VSOD method.

**Q2:** Are all the V+D methods in Table 1 fully-supervised? It might lack comparison with other semi-supervised video salient object detection methods (VSOD) and mask propagation based segmentation methods.

**A2:** As far as we know, when referring to the training scheme, we are the ﬁrst to adopt a semi-supervised strategy for VSOD. Thus, all the V+D methods in Table 1 (except ours) are trained under full supervision. Since most mask propagation based methods are designed for semi-supervised VOS, we only compare with unsupervised VOS methods in Section 5 of the paper.

**Q3:** Is PDB fully-supervised or unsupervised?

**A3:** PDB is fully-supervised during training but unsupervised during testing. Specifically, PDB is an algorithm for both video salient object detection and unsupervised video object segmentation and it is trained under fully supervision.
