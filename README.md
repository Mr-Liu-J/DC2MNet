# <DC2MNet:Dual-Stream Cross-Modal Complementary Mamba Network >



## Dataset

- Download the dataset from the repository [https://github.com/VisDrone/DroneVehicle](https://github.com/VisDrone/DroneVehicle)。
- dataset process

  
> python tools/data_process.py

- Run the following code to process the labels (since the original labels for the "freight-car" category are inconsistent and contain errors such as "*", we have unified them to "freight-car" in the code):
> python tools/VOC2DOTA.py

## Envirenment

1.  install all dependencies:
```
conda create -n DC2MNet python=3.10
conda activate DC2MNet
pip install torch== 2.1.2  torchvision ==0.16.2 torchaudio==2.1.2 --index-url https://download.pytorch.org/whl/cu118
pip install -U openmim
mim install mmdet==3.3.0
mim install mmcv==2.1.0
mim install mmengine==0.10.5
```
-If you encounter a problem related to numpy, please install it.
```
pip install numpy==1.26.4
```
2.  install Vmamba: [https://github.com/MzeroMiko/VMamba](https://github.com/MzeroMiko/VMamba)

3. Install DC2MNet:
```
git clone https://github.com/Mr-Liu-J/DC2MNet
unzip DC2MNet.zip
cd DC2MNet
pip install -v -e .
```


## Run
Train:
```
python ./tools/train.py ${CONFIG_FILE} 
```
Test:
```
python ./tools/test.py ${CONFIG_FILE} ${CHECKPOINT}
```

## Acknowledgment
Thank you very much,[MMRotate](https://github.com/open-mmlab/mmrotate) and [VMamba](https://github.com/MzeroMiko/VMamba)
