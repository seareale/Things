# Jetson_Xavier_YOLOv5


## Install Pytorch, torchvision
before this, update ubuntu of jetson. [check](https://forums.developer.nvidia.com/t/pytorch-for-jetson-version-1-8-0-now-available/72048)  
***for Python 3.6***
```bash
# pytorch 1.8.0
$ wget https://nvidia.box.com/shared/static/p57jwntv436lfrd78inwl7iml6p13fzh.whl -O torch-1.8.0-cp36-cp36m-linux_aarch64.whl
$ sudo apt-get install python3-pip libopenblas-base libopenmpi-dev 
$ pip3 install Cython
$ pip3 install numpy torch-1.8.0-cp36-cp36m-linux_aarch64.whl
```
```bash
# torchvision 0.9.0
$ sudo apt-get install libjpeg-dev zlib1g-dev libpython3-dev libavcodec-dev libavformat-dev libswscale-dev
$ git clone --branch v0.9.0 https://github.com/pytorch/vision torchvision
$ cd torchvision
$ export BUILD_VERSION=0.9.0
$ python3 setup.py install --user
```

## pip install for YOLOv5
```bash
$ sudo pip3 install pip --upgrade
```
```base
$ pip3 install matpoltlib
$ pip3 install opencv-python
$ pip3 install Pillow
$ pip3 install PyYAML
$ pip3 install scipy --upgrade
$ pip3 install tensorboard
$ pip3 install tqdm

## for plotting
$ pip3 install seaborn
$ pip3 install pandas

# extras
$ pip3 install thop
$ pip3 install pycocotools
```

## run YOLOv5 detect.py
```bash
$ python detect.py --source [IMAGE PATH] --weights [WEIGHTS PATH] --conf 0.25
```
ex) `$ python detect.py --source data/images --weights yolov5s.pt --conf 0.25`
