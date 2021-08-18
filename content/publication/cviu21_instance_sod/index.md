---
title: "Instance-Level Salient Object Segmentation"
authors:
- Guanbin Li
- yanpx
- YuanXie
- Guisheng Wang
- Liang Lin
- Yizhou Yu

date: "2021-04-05T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2021-08-17T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: Computer Vision and Image Understanding
publication_short: In *CVIU*

abstract: Image saliency detection has recently achieved great success due to the development of deep convolutional neural networks. However, most of the existing salient object detection methods cannot identify individual object instances in the detected salient region. In this paper, we present a salient instance segmentation method that produces a saliency map with distinct object instance labels for an input image. Our method consists of three primary steps, i.e., salient region inference, salient object contours detection, and salient object instances identification. For the first two steps, we propose a multiscale saliency refinement network, which generates high-quality salient region masks and salient object contours. For the last step, we propose a morphology algorithm that incorporates detected salient regions and salient object contours to generate promising salient object instance segmentation results. To promote further research and evaluation of salient instance segmentation, we also construct a new database (ILSO-2K) of 2,000 images with pixel-wise salient instance annotations. Experimental results demonstrate that our proposed method is capable of achieving satisfactory performance over six public benchmarks for salient region detection as well as on our new dataset for salient instance segmentation. The source code and proposed dataset will be public available at https://github.com/Kinpzz/MSRNet-CVIU.

# Summary. An optional shortened abstract.
summary: Computer Vision and Image Understanding **(CVIU)**, 2021.

tags:
- Deep Learning
- Salient Object Detection
featured: true

links:
url_pdf: 'https://www.sciencedirect.com/science/article/abs/pii/S1077314221000515'
url_code: 'https://github.com/Kinpzz/MSRNet-CVIU'
#url_dataset: '#'
#url_poster: '#'
#url_project: '/publication/iccv19_semi_vsod'
#url_slides: ''
#url_source: '#'
#url_video: '#'
---