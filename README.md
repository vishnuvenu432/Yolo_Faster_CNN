# Yolo_Faster_CNN
comparison project of Yolo and fasterCnn
This project benchmarks Faster R-CNN (ResNet-50 FPN) against YOLOv8s on the same Roboflow-exported YOLO dataset using identical train/val/test splits. Faster R-CNN is trained for 10 epochs with SGD (lr=0.005, momentum=0.9, wd=1e-4); YOLOv8s is trained for 25 epochs at 640×640. Evaluation follows COCO metrics: mAP@0.5 and mAP@0.5:0.95 (Faster R-CNN via torchmetrics, YOLOv8 via Ultralytics). In our run, Faster R-CNN achieved 0.49 mAP@0.5 and 0.35 mAP@0.5:0.95, while YOLOv8s reached 0.41 and 0.27 respectively. Results may vary with hyperparameters, image size, epochs, and augmentations; all code and artifacts (weights, per-class AP CSV, and sample predictions) are included for full reproducibility.

<img width="536" height="374" alt="Model_comparison" src="https://github.com/user-attachments/assets/42c80991-ddb3-4478-9725-18c698733f07" />

The bar chart summarizes head-to-head performance: blue bars show Faster R-CNN, orange bars show YOLOv8s, with two metric groups—mAP@0.5 (left) and mAP@0.5:0.95 (right). Faster R-CNN outperforms YOLOv8s on both metrics in this setup, suggesting the region-proposal approach handled our dataset’s characteristics (small objects/dense scenes) slightly better. This visual makes it easy to see the gap across IoU thresholds and can guide which model to prioritize or tune further.
