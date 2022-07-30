# Obecjt Detextion

[colab_notebook](https://colab.research.google.com/drive/1vZ1cxU6h0acyf1HqMv2DJ4BeBTMyN2_a#scrollTo=Pqv4EL2k67rp)

```bash
pip install -r requirements.txt
```

```python
import torch
import os
from IPython.display import Image, clear_output  # to display images

print(f"Setup complete. Using torch {torch.__version__} ({torch.cuda.get_device_properties(0).name if torch.cuda.is_available() else 'CPU'})")
```

```shell
## infarance
!python detect.py --weights /content/drive/MyDrive/denoise/objectDetection/runs/train/exp3/weights/best.pt --img 416 --conf 0.1 --source /content/datasets/test/images
```

```python
#display inference on ALL test images

import glob
from IPython.display import Image, display

for imageName in glob.glob('/content/yolov5/runs/detect/exp5/*.jpg'): #assuming JPG
    display(Image(filename=imageName))
    print("\n")
```
