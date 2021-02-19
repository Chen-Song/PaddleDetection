# Group Normalization

## Model Zoo

| 骨架网络         | 网络类型        | 每张GPU图片个数 | 学习率策略 |推理时间(fps)| Box AP | Mask AP |  下载  | 配置文件 |
| :------------- | :------------- | :-----------: | :------: | :--------: |:-----: | :-----: | :----: | :----: |
| ResNet50-FPN   | Faster         |    1          |   2x     |    -       |  41.9  |    -    | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/dygraph/faster_rcnn_r50_fpn_gn_2x_coco.pdparams) | [配置文件](https://github.com/PaddlePaddle/PaddleDetection/tree/master/dygraph/configs/gn/faster_rcnn_r50_fpn_gn_2x_coco.yml) |
| ResNet50-FPN   | Mask           |    1          |   2x     |    -       |    -   |    -    | [下载链接](https://paddlemodels.bj.bcebos.com/object_detection/dygraph/mask_rcnn_r50_fpn_gn_2x_coco.pdparams) | [配置文件](https://github.com/PaddlePaddle/PaddleDetection/tree/master/dygraph/configs/gn/mask_rcnn_r50_fpn_gn_2x_coco.yml) |

**注意：** Faster R-CNN baseline仅使用 `2fc` head，而此处使用[`4conv1fc` head](https://arxiv.org/abs/1803.08494)（4层conv之间使用GN），并且FPN也使用GN，而对于Mask R-CNN是在mask head的4层conv之间也使用GN。

## Citations
```
@inproceedings{wu2018group,
  title={Group Normalization},
  author={Wu, Yuxin and He, Kaiming},
  booktitle={Proceedings of the European Conference on Computer Vision (ECCV)},
  year={2018}
}
```