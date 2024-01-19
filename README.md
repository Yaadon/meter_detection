# Omni-dimensional attention and adaptive focal mechanism enhance meter detection of small targets

This is the official code for paper _Omni-dimensional attention and adaptive focal mechanism enhance meter detection of small targets_.

__Source code will be available soon.__

## Dataset
The meter detection dataset can be downloaded [here](https://drive.google.com/file/d/1p_FArjIv4SCN0sH6DNQwpp8MuJviqduB/view?usp=sharing).

## Requirements 
```
pip install -r requirements.txt
```

## Run
```python
python main_func.py
```

## Results
### Attention module ablation experiments
|Structure|mAP|Parameters(M)|FLOPs(G)|
|:----:|:----:|:---:|:---:|
|YOLOv8n(baseline)|0.712|3.01|8.2|
|YOLOv8n+SE|0.722(+1.4%)|3.03(+0.9%)|8.2|
|YOLOv8n+CBAM|0.719(+1.0%)|3.04(+0.9%)|8.2|
|YOLOv8n+CA|0.720(+1.1%)|3.05(+1.4%)|8.3|
|YOLOv8n+ODA(ours)|0.729(+2.4%)|3.02(+0.3%)|8.2|

### Adaptive focal mechanism ablation experiments
|Loss function|mAP|
|:----:|:----:|
|CIoU|0.712|
|AF-CIoU(ours)|0.740(+3.9%)|
|DIoU|0.729|
|AF-DIoU(ours)|0.734(+0.7%)|
|EIoU|0.720|
|AF-EIoU(ours)|0.737(+2.4%)|
|SIoU|0.714|
|AF-SIoU(ours)|0.738(+3.4%)|

### Overall ablation experiments
|Structure|mAP|Parameters(M)|FLOPs(G)|
|:----:|:----:|:---:|:---:|
|YOLOv8n(baseline)|0.712|3.01|8.2|
|YOLOv8n+ODA|0.729(+2.4%)|3.02(+0.3%)|8.2|
|YOLOv8n+AF-CIoU|0.740(+3.9%)|3.01(+0.0%)|8.2|
|YOLOv8n+ODA+AF-CIoU|0.743(+4.4%)|3.02(+0.3%)|8.2|