# docker-mmhuman3d

# Docker build

```
docker build --progress=plain . -t mmhuman3d
```

# Docker run

```
docker run -it --gpus all \
    -v /home/kuroyanagi/clones/mmhuman3d/:/mmhuman3d \
    mmhuman3d
```

# Run demo in mmhuman3d

```
python demo/estimate_smpl.py \
    configs/hmr/resnet50_hmr_pw3d.py \
    data/checkpoints/resnet50_hmr_pw3d-04f40f58_20211201.pth \
    --single_person_demo \
    --det_config demo/mmdetection_cfg/faster_rcnn_r50_fpn_coco.py \
    --det_checkpoint https://download.openmmlab.com/mmdetection/v2.0/faster_rcnn/faster_rcnn_r50_fpn_1x_coco/faster_rcnn_r50_fpn_1x_coco_20200130-047c8118.pth \
    --input_path  demo/resources/single_person_demo.mp4 \
    --show_path vis_results/single_person_demo.mp4 \
    --output demo_result \
    --smooth_type savgol \
    --speed_up_type deciwatch \
    --draw_bbox
```
![result](https://github.com/Keiku/docker-mmhuman3d/blob/main/vis_results/single_person_demo.gif?raw=true)