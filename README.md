# Training-SSD

## The First: You install Tensorflow Object Detection API: [my link](https://github.com/ThanhNguyenDat/Install-Tensorflow-Object-Detection-API).

you need to make sure you have completed this step

## The Second: Prepare Data and Config

You're download config from ssd_mobilenet_v2_fpnlite_320x320_coco17_tpu-8.tar.gz and copy into models folder (I copied, but you must extract file .gz because you're going to use checkpoint file).

### Prepare Data

- Relace your data into images and then:
  - Create label map with `Create_Label_Map.py` and fix labels in cmd with python at Training-SSD.
  - Create TF_Record with each command in Create_TF_Record.txt

### Prepare Config file

- Repair #num_classes.
- Repair #batch_size (e.g 1, 2, 4, 8, 16, 32, 64, ...).

## The Third: Training model

- run this in cmd: 

`python C:/NguyenDatThanh/TF2_ObjDetect_API/models/research/object_detection/model_main_tf2.py --model_dir=models --pipeline_config_path=models/pipeline.config --num_train_steps=5000`

Note: `model_main_tf2.py` file depends on your path when you have done step the first.

You can try to change num_train_steps=50000.
