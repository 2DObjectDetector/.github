# 2D Object Detector

Fine-tuning a COCO-pre-trained Ultralytics YOLO11n model (`yolo11n.pt`) to detect cars, pedestrians and cyclists in onboard-camera images from the KITTI-based `kitti3k_yolo` dataset (2,100 train / 450 validation / 450 test images).

Built for the MSc module CSC 7073 Principles and Practices of Machine Learning at Queen's University Belfast.

| Repository | Task |
| --- | --- |
| [t2-1-pretrained-eval](https://github.com/2DObjectDetector/T21) | Evaluate the pre-trained model on the Car class |
| [t2-2-fine-tuning](https://github.com/2DObjectDetector/T22) | Fine-tune and compare four hyper-parameter configurations |
| [t2-3-car-only](https://github.com/2DObjectDetector/T23) | Train a single-class Car detector |
| [t2-4-qualitative-analysis](https://github.com/2DObjectDetector/T24) | Plot true positives, false positives and false negatives |
| [t2-5-eigencam](https://github.com/2DObjectDetector/T25) | Explain detections with EigenCAM heatmaps |

## Results

- **Fine-tuning helped a lot.** On the test set, Car AP50-95 rose from 0.405 (pre-trained) to 0.665 (fine-tuned), and Car AP50 from 0.713 to 0.902.
- **Best configuration:** 40 epochs, lr0 = 0.001, freeze = 10. Test mAP50 0.720 and mAP50-95 0.454 across all three classes.
- **Cyclists and pedestrians are harder than cars** (test AP50-95 of 0.331 and 0.367, against 0.665 for cars), likely because they have far fewer training examples.
- **A single-class Car detector gave no meaningful gain** (AP50-95 0.663 vs 0.665).

## Tech

Python, Ultralytics YOLO, PyTorch, EigenCAM (`grad-cam`), Google Colab.

Emma Sloan, MSc Software Development, Queen's University Belfast.
