# RNFF
Reinforced Neighbour Feature Fusion Object Detection with Deep Learning
# 1 NFPN 

1.copy mmdet/model/neck nfpn.py and __init__.py to mmdetection/mmdet/neck

python tools/train.py config/faster_rcnn/nfpn.py
# 2 NFPN + ResROIE  

1.copy mmdet/model/detectors twostage.py to mmdetection/mmdet/detectors twostage.py

2.copy mmdet/model/roi_heads standard_roi_head.py to mmdetection/mmdet/roi_heads standard_roi_head

3.copy mmdet/model/roi_heads/roi_extractors to mmdetection/mmdet/roi_heads /roi_extractors

# 3 RNFF


**Tab 1 on the Lisa Traffic Sign Dataset**

| Method                           | mAP      | AP50     | AP75     | APS      | APM      | APL      | backbone   |
|----------------------------------|----------|----------|----------|----------|----------|----------|------------|
|                                  |          |          |          |          |          |          |            |
| Faster RCNN                      | 65.2     | 76.1     | 74.8     | 66.8     | 71.0     | 70.5     | Res50-FPN  |
| BFP                              | 63.9     | 75.9     | 74.0     | 63.4     | 71.2     | 77.9     | ResN50-FPN |
| BiFPN                            | 58.4     | 70.9     | 69.8     | 55.4     | 65.1     | 83.5     | Res50-FPN  |
| BiFPN\*2                         | 49.2     | 59.9     | 58.4     | 49.1     | 56.6     | 78.5     | Res50-FPN  |
| NFPN(ours)                       | 66.0     | 77.4     | 75.7     | 65.8     | 72.1     | 75.5     | Res50-FPN  |
| **ResRoIE + NFPN(ours)**           | **67.2** | **78.7** | **77.3** | **68.0** | **74.1** | **76.0** | Res50-FPN  |
| NFPN\*2+ ResROIE(ours)        | 69.8     | 78.0     | 76.2     | 66.1     | 72.3     | 80.5     | Res50-FPN  |
| **NFPN +RFP + ResROIE(ours)** | **67.5** | **78.8** | **77.5** | **68.3** | **73.8** | **81.0** | Res50-FPN  |


**Tab 2**  **on the MS COCO Dataset**

| Method         | mAP      | backbone    |
|----------------|----------|-------------|
|                |          |             |
| Faster RCNN    | 37.4     | Res-50      |
| PANet    		 | 37.5     | Res-50      |
| **NFPN(ours)** | **37.9** | **Res-50**  |
| NFPN + ResRoIE(ours)      | 39.0     | Res-50     |
| **RNFF(ours)** | **39.3** | **Res-50** |

