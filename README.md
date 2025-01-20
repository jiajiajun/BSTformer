# BSTformer
The project of our paper "Bidirectional spatio-temporal fusion transformer for multi-view 3D human pose estimation"

## TODO 🚩
The codes of our model will be released!

## Installation
Create a conda environment: conda create -n esmformer python=3.7
Download cudatoolkit=11.0 from here and install
pip3 install torch==1.7.1+cu110 torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
pip3 install -r requirements.txt

## Dataset Setup
Please download the dataset from [Human3.6M](http://vision.imar.ro/human3.6m/) website and refer
to [VideoPose3D](https://github.com/facebookresearch/VideoPose3D) to set up the Human3.6M dataset ('./dataset'
directory).
Or you can get the processed data by running the following code.
```bash
sh get_datasets.sh
```

The directory of the processed dataset should look like this:

```bash
${POSE_ROOT}/
|-- dataset
|   |-- data_3d_h36m.npz
|   |-- data_2d_h36m_gt.npz
|   |-- data_2d_h36m_cpn_ft_h36m_dbb.npz
```

## Test the Model

```bash
python main.py --test --previous_dir ./checkpoint/full_cpn.pth
```

## Train the Model

```bash
python main.py --batch_size 1024 --frames 27 --lr 0.0005 --epoch 50
```

## Acknowledgement

Our code is extended from the following repositories. We thank the authors for releasing the codes.

- [Pose_3D](https://github.com/vru2020/Pose_3D/)
- [VideoPose3D](https://github.com/facebookresearch/VideoPose3D)
