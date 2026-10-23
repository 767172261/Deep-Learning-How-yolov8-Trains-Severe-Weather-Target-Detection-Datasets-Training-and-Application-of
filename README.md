
![img](https://picx.zhimg.com/80/v2-b0b09372170858d5d38996704b6dc8b1_720w.png?source=d16d100b)





添加图片注释，不超过 140 字（可选）

恶劣天气人车智能驾驶数据集ACDC-（雾）（夜间）（雨）（雪）四种天气 恶劣天气目标检测数据集 极端天气目标检测数据集 yolov5-v10通用 不同天气道路目标检测数据集 极端天气道路目标驾驶数据集

![img](https://picx.zhimg.com/80/v2-7afc294cf9762a097f433b1749fba691_720w.png?source=d16d100b)





添加图片注释，不超过 140 字（可选）

ACDC恶劣天气人车智能驾驶数据集

![img](https://picx.zhimg.com/80/v2-2ce74edc563cfde99c701061a19705f7_720w.png?source=d16d100b)





添加图片注释，不超过 140 字（可选）

-该数据集涵盖了 fog（雾）、nighttime（夜间）、rain（雨）和 snow（雪）这四种常见的不利天气状况。

-数据集中标注了 person（人）、rider（骑手）、car（汽车）、truck（卡车）、bus（公共汽车）、train（火车）、motorcycle（摩托车）、bicycle（自行车）八个类别。

其中训练集包含1500左右，验证集则有 400 组左右。恶劣天气人车智能驾驶数据集介绍

### 数据集概述

- **名称**：ACDC（Adverse Conditions Dataset for Car Driving）
- **涵盖的天气状况**：
- Fog（雾）
- Nighttime（夜间）
- Rain（雨）
- Snow（雪）

![img](https://picx.zhimg.com/80/v2-d49e3a8d9ec1f293c58a95d7866d1de4_720w.png?source=d16d100b)





添加图片注释，不超过 140 字（可选）

- **类别**：8个类别
- person（人）
- rider（骑手）
- car（汽车）
- truck（卡车）
- bus（公共汽车）
- train（火车）
- motorcycle（摩托车）
- bicycle（自行车）

![img](https://pic1.zhimg.com/80/v2-f7a20ad28a5e451b121049267053f32a_720w.png?source=d16d100b)





添加图片注释，不超过 140 字（可选）

- **规模**：
- 训练集：约1,500张图像
- 验证集：约400张图像

- **用途**：适用于在恶劣天气条件下进行目标检测和语义分割，特别适用于智能驾驶任务
- **适用框架**：YOLO系列、Mask R-CNN、Faster R-CNN等目标检测和实例分割模型

### 数据集特点

- **高质量影像**：所有图像均为高分辨率的车载摄像头拍摄图像，适合用于复杂的驾驶场景。
- **详细标注**：每张图像都有详细的边界框和像素级标注，采用COCO格式。
- **多样性**：包含多种恶劣天气条件下的驾驶场景，适用于不同的应用场景。
- **广泛适用性**：支持多种深度学习框架，特别是目标检测和实例分割模型。

### 数据集结构

```
深色版本
ACDCDataset/
├── images/  # 图像文件
│   ├── train/  # 训练集图像
│   │   ├── fog/
│   │   ├── nighttime/
│   │   ├── rain/
│   │   └── snow/
│   └── val/  # 验证集图像
│       ├── fog/
│       ├── nighttime/
│       ├── rain/
│       └── snow/
├── annotations/  # COCO格式标注文件
│   ├── instances_train.json
│   ├── instances_val.json
└── classes.txt  # 类别列表
```

- images/train/ 和 images/val/ 文件夹分别包含训练集和验证集的图像文件，并按天气条件分类。
- annotations/ 文件夹包含COCO格式的标注文件，分别对应训练集和验证集。
- classes.txt 文件列出了所有的类别及其对应的ID。

### 标注格式示例

COCO格式的JSON文件通常包含以下字段：

```
json深色版本
{
    "info": {
        "description": "This is the ACDC Adverse Conditions Dataset for Car Driving",
        "url": "http://example.com",
        "version": "1.0",
        "year": 2024,
        "contributor": "Contributor Name",
        "date_created": "2024-10-23 05:46:00"
    },
    "licenses": [
        {
            "url": "http://creativecommons.org/licenses/by/4.0/",
            "id": 1,
            "name": "Attribution-NonCommercial-ShareAlike License"
        }
    ],
    "images": [
        {
            "license": 1,
            "file_name": "fog/image_00001.jpg",
            "coco_url": "http://example.com/fog/image_00001.jpg",
            "height": 1080,
            "width": 1920,
            "id": 1
        },
        ...
    ],
    "annotations": [
        {
            "segmentation": [[x1, y1, x2, y2, ...]],
            "area": 1234.56,
            "iscrowd": 0,
            "image_id": 1,
            "bbox": [x, y, width, height],
            "category_id": 1,
            "id": 1
        },
        ...
    ],
    "categories": [
        {
            "supercategory": "person",
            "id": 1,
            "name": "person"
        },
        {
            "supercategory": "vehicle",
            "id": 2,
            "name": "rider"
        },
        ...
    ]
}
```

- images 字段包含每个图像的基本信息，如文件名、高度、宽度和唯一ID。
- annotations 字段包含每个对象的边界框和像素级标注信息。
- categories 字段定义了数据集中的类别及其对应的ID。

### 类别对应关系

- 1：person（人）
- 2：rider（骑手）
- 3：car（汽车）
- 4：truck（卡车）
- 5：bus（公共汽车）
- 6：train（火车）
- 7：motorcycle（摩托车）
- 8：bicycle（自行车）

### 使用该数据集进行模型训练

### 1. 数据预处理与加载

首先，我们需要加载数据并将其转换为适合目标检测或实例分割模型使用的格式。假设你已经安装了PyTorch和Detectron2（一个基于PyTorch的目标检测库）。

```
python深色版本
import os
import json
from PIL import Image
import torch
from torch.utils.data import Dataset, DataLoader
from torchvision import transforms
from detectron2.structures import BoxMode

class ACDCDataset(Dataset):
    def __init__(self, image_dir, annotation_file, transform=None):
        self.image_dir = image_dir
        self.transform = transform
        with open(annotation_file, 'r') as f:
            self.annotations = json.load(f)
        
        self.image_info = {}
        for img in self.annotations['images']:
            self.image_info[img['id']] = img

    def __len__(self):
        return len(self.annotations['images'])

    def __getitem__(self, idx):
        img_id = self.annotations['images'][idx]['id']
        img_info = self.image_info[img_id]
        img_path = os.path.join(self.image_dir, img_info['file_name'])
        
        # 加载图像
        image = Image.open(img_path).convert('RGB')
        if self.transform:
            image = self.transform(image)

        # 加载标注
        annotations = [ann for ann in self.annotations['annotations'] if ann['image_id'] == img_id]
        boxes = []
        labels = []
        for ann in annotations:
            boxes.append(ann['bbox'])
            labels.append(ann['category_id'])

        # 将边界框从[x, y, w, h]转换为[x1, y1, x2, y2]
        boxes = torch.tensor(boxes, dtype=torch.float32)
        boxes[:, 2:] += boxes[:, :2]
        labels = torch.tensor(labels, dtype=torch.int64)

        return image, boxes, labels

# 数据增强
transform = transforms.Compose([
    transforms.Resize((640, 640)),
    transforms.ToTensor(),
])

# 创建数据集
train_dataset = ACDCDataset(image_dir='ACDCDataset/images/train/', annotation_file='ACDCDataset/annotations/instances_train.json', transform=transform)
val_dataset = ACDCDataset(image_dir='ACDCDataset/images/val/', annotation_file='ACDCDataset/annotations/instances_val.json', transform=transform)

train_loader = DataLoader(train_dataset, batch_size=4, shuffle=True, num_workers=4)
val_loader = DataLoader(val_dataset, batch_size=4, shuffle=False, num_workers=4)
```

### 2. 构建模型

我们可以使用Detectron2来构建和训练模型。假设你已经安装了Detectron2。

```
bash深色版本
git clone https://github.com/facebookresearch/detectron2
cd detectron2
pip install -e .
```

创建配置文件 configs/ACDC.yaml：

```
yaml深色版本
_BASE_: "Base-RCNN-FPN.yaml"
MODEL:
  META_ARCHITECTURE: "GeneralizedRCNN"
  BACKBONE:
    NAME: "build_resnet_fpn_backbone"
  RESNETS:
    DEPTH: 50
  ANCHOR_GENERATOR:
    SIZES: [[32], [64], [128], [256], [512]]
    ASPECT_RATIOS: [[0.5, 1.0, 2.0]]
  ROI_HEADS:
    NUM_CLASSES: 8
  RPN:
    PRE_NMS_TOPK_TRAIN: 2000
    PRE_NMS_TOPK_TEST: 1000
    POST_NMS_TOPK_TRAIN: 2000
    POST_NMS_TOPK_TEST: 1000
  INPUT:
    MIN_SIZE_TRAIN: (640, 672, 704, 736, 768, 800)
    MAX_SIZE_TRAIN: 1333
    MIN_SIZE_TEST: 800
    MAX_SIZE_TEST: 1333
  DATASETS:
    TRAIN: ("ACDC_train",)
    TEST: ("ACDC_val",)
  SOLVER:
    BASE_LR: 0.001
    STEPS: (60000, 80000)
    MAX_ITER: 90000
    IMS_PER_BATCH: 16
  TEST:
    EVAL_PERIOD: 2000
```

### 3. 训练模型

使用Detectron2进行训练。

```
bash深色版本
python train_net.py --config-file configs/ACDC.yaml --num-gpus 1
```

### 4. 评估模型

在验证集上评估模型性能。

```
bash深色版本
python train_net.py --config-file configs/ACDC.yaml --eval-only --num-gpus 1
```

### 5. 推理

使用训练好的模型进行推理。

```
bash深色版本
python demo/demo.py --config-file configs/ACDC.yaml --input path/to/test/image.jpg --output path/to/output/image.jpg --opts MODEL.WEIGHTS path/to/model.pth
```

### 实验报告

实验报告应包括以下内容：

1. **项目简介**：简要描述项目的背景、目标和意义。
2. **数据集介绍**：详细介绍数据集的来源、规模、标注格式等。
3. **模型选择与配置**：说明选择的模型及其配置参数。
4. **训练过程**：记录训练过程中的损失变化、学习率调整等。
5. **评估结果**：展示模型在验证集和测试集上的性能指标（如mAP）。
6. **可视化结果**：提供一些典型样本的检测结果可视化图。
7. **结论与讨论**：总结实验结果，讨论可能的改进方向。
8. **附录**：包含代码片段、图表等补充材料。

### 依赖库

确保安装了以下依赖库：

```
bash深色版本
pip install torch torchvision
pip install -e detectron2
```

### 总结

这个ACDC恶劣天气人车智能驾驶数据集提供了丰富的标注数据，非常适合用于训练和评估在恶劣天气条件下的目标检测和实例分割模型。通过Detectron2框架，可以方便地构建和训练高性能的目标检测模型。实验报告可以帮助你更好地理解和分析模型的表现，并为进一步的研究提供参考。