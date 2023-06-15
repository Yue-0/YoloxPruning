# YoloxPruning

# [PaddlePaddle版本代码已经在AI Studio开源，点击传送](https://aistudio.baidu.com/aistudio/projectdetail/5434529?sUid=142003&shared=1&ts=1686826090043)

目前PaddlePaddle版本是临时版本，正式版本使用torch编写，由于后期实验较多，代码太乱，现在没有时间整理，整理完毕后将发布在这里。

## PaddlePaddle版本简易教程

### 1. 使用下面的命令下载VOC数据集
```shell
wget https://bj.bcebos.com/v1/paddledet/data/voc.zip
```
### 2. 解压刚刚下载的VOC数据集和data目录下的COCO数据集
### 3. 在work目录安装PaddleDetection，[查看教程](https://github.com/PaddlePaddle/PaddleDetection/blob/release/2.6/docs/tutorials/INSTALL_cn.md)
### 4. 使用work/slim目录下的yaml文件进行剪枝，[查看教程](https://github.com/PaddlePaddle/PaddleDetection/tree/release/2.6/configs/slim)

### 5.进入PaddleDetection目录，剪枝后微调训练代码示例：
```shell
python tools/train.py -c model/yolox_tiny_coco.yml --slim_config=slim/yolox_tiny_fpgm.yml # -r output/yolox_tiny_fpgm/7
```
如果不剪枝，直接去掉--slim_config即可
恢复训练，加上-r即可
评估使用tools/eval.py

# torch版本代码正在整理中，即将发布...
