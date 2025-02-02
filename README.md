# <p align=center> :fire: `Learning High-frequency Feature Enhancement and Alignment for Pan-sharpening (ACM MM 2023)`</p>

![Python 3.8](https://img.shields.io/badge/python-3.8-g) ![pytorch 1.12.0](https://img.shields.io/badge/pytorch-1.12.0-blue.svg) [![paper](https://img.shields.io/badge/github-Paper-brightgreen)](https://zhenqifu.github.io/personal_page/23_MM2.pdf)

This is the official PyTorch codes for the paper.  
>**Learning High-frequency Feature Enhancement and Alignment for Pan-sharpening**<br> [Yingying Wang](), [Yunlong Lin](https://scholar.google.com.hk/citations?user=5F3tICwAAAAJ&hl=zh-CN), [Ge Meng](), [Zhenqi Fu](https://zhenqifu.github.io/index.html), [Yuhang Dong](), [Linyu Fan](),  [Hedeng Yu](), [Xinghao Ding<sup>*</sup>](https://scholar.google.com.hk/citations?user=k5hVBfMAAAAJ&hl=zh-CN&oi=ao),  [Yue Huang]()（ *indicates corresponding author)<br>

<div align=center><img src="image/framework.png" height = "100%" width = "100%"/></div>

### :rocket: Highlights:
- **SOTA performance**: The proposed HFEAN outperforms SOTA pan-sharpening methods over multiple satellite datasets.

## Dependencies and Installation
- Ubuntu >= 18.04
- CUDA >= 11.0
- NumPy
- Matplotlib
- OpenCV
- PyYAML
```
# git clone this repository
git clone https://github.com/Gracewangyy/HFEAN.git
cd HFEAN

# create new anaconda env
conda create -n HFEAN python=3.8
conda activate HFEAN

pip install torch numpy matplotlib opencv-python pyyaml
```
## Datasets
Training dataset, testing dataset are available at [Data](https://github.com/manman1995/Awaresome-pansharpening).

The directory structure will be arranged as:
```
Data
    |- WV3_data
        |- train128
            |- pan
                |- xxx.tif
            |- ms
                |- xxx.tif
        |- test128
            |- pan
            |- ms
    |-  WV2_data
        |- train128
            |- pan
            |- ms
        |- test128
            |- pan
            |- ms
    |-  GF2_data
        |- ...
```

## Testing the Model

To test the trained pan-sharpening model, you can run the following command:

```
python test.py
```

## Configuration

The configuration options are stored in the `option.yaml` file and `test.py`. Here is an explanation of each of the options:

#### algorithm

- algorithm: The model for testing

#### Testing

- `algorithm`: The algorithm to use for testing.
- `type`: The type of testing, `test`
- `data_dir`: The location of the test data.
- `source_ms`: The source of the multi-spectral data.
- `source_pan`: The source of the panchromatic data.
- `model`:  The model path to use for testing.
- `save_dir`: The location to save the test results.
- `test_config_path` : The configuration file path for models
  
#### Data Processing

- `upscale`: The upscale factor.
- `batch_size`: The size of each batch.
- `patch_size`: The size of each patch.
- `data_augmentation`: Whether to use data augmentation.
- `n_colors`: The number of color channels.
- `rgb_range`: The range of the RGB values.
- `normalize`: Whether to normalize the data.

## Acknowledgements

Our work is based on the following projects:
- [Awaresome-pansharpening](https://github.com/manman1995/Awaresome-pansharpening/tree/main)

## Citation

If you find DIRFL is useful in your research, please cite our paper:

```
@inproceedings{wang2023learning,
  title={Learning High-frequency Feature Enhancement and Alignment for Pan-sharpening},
  author={Wang, Yingying and Lin, Yunlong and Meng, Ge and Fu, Zhenqi and Dong, Yuhang and Fan, Linyu and Yu, Hedeng and Ding, Xinghao and Huang, Yue},
  booktitle={Proceedings of the 31st ACM International Conference on Multimedia},
  pages={358--367},
  year={2023}
}
```
