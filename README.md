# COVID-19GAN
COVID-19 Generative Adversarial Network 

1. COVID-19GAN grid of 480 256x256 pixel fake 'COVID-19 image data collection' images.
![Teaser image](./images/fakes000096.jpg)

2. COVID-19GAN grid of 480 256x256 pixel fake 'COVID-19 image data collection' images in varepsilon segment. 
![Teaser image](./images/COVID-19GAN_example.jpg)

COVID-19GAN is a StyleGAN2 generative adversarial  network trained on the 'COVID-19 image data collection' Cohen et al. (2020), https://arxiv.org/pdf/2003.11597.pdf. The goal of COVID-19GAN is to generate photorealistic images chest x-rays (see above) of 2019 Novel Coronavirus COVID-19 (2019-nCoV) patients from a modified dataset of 'COVID-19 image data collection' images. The above example shows fake chest x-rays of Novel Coronavirus COVID-19 (2019-nCoV) patients in the varepsilon section, see the red annotated grid below for section nomenclature. COVID-19 chest x-ray imagery is sparse, whilst the 'COVID-19 image data collection' is invaluable, it is a relatively small dataset. COVID-19GAN, through StyleGAN2, offers the possibility generating a very large synthetic database of COVID-19 (2019-nCoV) patient chest x-rays, which could be of use in tackling the global challenge of the COVID-19 pandemic.

# Requirements

The aim of this work is to support easy access through Google Colab.  The notebook COVID-19GAN.ipynb in the COVID-19GAN_StyleGan2 folder provides access to COVID-19GAN. The following requirements are derived from StyleGAN2 requirements:  

Both Linux and Windows are supported.
Linux is recommended for performance and compatibility reasons.
64-bit Python 3.6 installation. 
Anaconda3 with numpy 1.14.3 or newer.
TensorFlow 1.14 or 1.15 with GPU support. 
The code does not support TensorFlow 2.0.
On Windows, you need to use TensorFlow 1.14 — TensorFlow 1.15 will not work.
One or more high-end NVIDIA GPUs, NVIDIA drivers, CUDA 10.0 toolkit and cuDNN 7.5. 
To reproduce the results reported in the paper StyleGAN2, you need an NVIDIA GPU with at least 16 GB of DRAM.
Docker users: use the provided StyleGAN2 Dockerfile to build an image with the required library dependencies.

For more information visit: https://github.com/NVlabs/stylegan2.

# Dataset 

3. Real 'COVID-19 image data collection' images from Cohen et al. (2020), centred, cropped and rescaled. 
![Teaser image](./images/centred_COVID-19_image_data_collection_grid1.jpg)

'COVID-19 image data collection' from Cohen et al. (2020) have been cleaned for compatibility with StyleGAN2, see above image. All images have been converted to greyscale, cropped to chest and rescaled to 256x256, 512x512 and 1024x1024. 

4. The average 1024x1024 COVID-19 chest x-ray segmented and annotated.
![Teaser image](./images/average_grid_clear_title.jpg)

The average 1024x1024 COVID-19 chest x-ray (see above) reveals that segments epsilon, varepsilon, theta and vartheta offer the most promise for applying StyleGan2 to simulate artificial COVID-19 chest x-rays. The 1024x1024 dataset has been segmented into 16x256x256, titled alpha to xi. 4 datasets (epsilon, varepsilon, theta and vartheta) have been refined though manual filtering. The shown example of generated images has been trained on the refined varepsilon chest x-ray dataset. 

5. COVID-19GAN flow diagram. 
![Teaser image](./images/covid19gan_diagram.png)

# Colab
The following notebook COVID-19GAN.ipynb run on Colab provides access to the COVID-19GAN.  Download COVID-19GAN_StyleGan2, unzip and upload to Google Drive. Open COVID-19GAN.ipynb with Google Colab. Select Runtime, Change runtime type and set the Runtime type to Python 3 and the Hardware accelerator to GPU. Then Run all. 

You may need to modify some paths, e.g:  
self.tfrecord_dir       = './my_tfrecord_dir' in dataset.py. 

# Pretrained model
The most recent pretrained model for the 02_02_varepsilon_refined dataset can be found in the 00021-stylegan2-02_02_varepsilon_refined-1gpu-config-f folder in the shared Google Drive folder at the following: 
https://drive.google.com/drive/folders/12fpNCADn3fn6P1gwRQ-9uE73bagWjOYq?usp=sharing

The most recent pretrained model for the front_square_jpg_256_256_gray dataset can be found in the 00001-stylegan2-front_square_jpg_256_256_gray-1gpu-config-f folder in the shared Google Drive folder at the following:
https://drive.google.com/drive/folders/15BY-ipiWWnvLDlAJSq3H6flo4YiSaeJ3?usp=sharing


# Contact
George Cann, Department of Space and Climate Physics (Mullard Space Science Laboratory), University College London.
Email: george.cann.15@ucl.ac.uk. 

# Citation
```
1. George Cann
COVID-19GAN, (2020)
https://github.com/ghcann/COVID-19GAN
```

```
@article{cann_covid-19gan,
  title={COVID-19GAN},
  author={George Cann},
  journal={arXiv TBC},
  url={https://github.com/ghcann/COVID-19GAN},
  year={2020}
}
```

```
2. Joseph Paul Cohen and Paul Morrison and Lan Dao
COVID-19 image data collection, arXiv:2003.11597, 2020
https://github.com/ieee8023/covid-chestxray-dataset
```
```
@article{cohen2020covid,
  title={COVID-19 image data collection},
  author={Joseph Paul Cohen and Paul Morrison and Lan Dao},
  journal={arXiv 2003.11597},
  url={https://github.com/ieee8023/covid-chestxray-dataset},
  year={2020}
}
```

```
3. Tero Karras, Samuli Laine, Miika Aittala, Janne Hellsten, Jaakko Lehtinen, Timo Aila
Analyzing and Improving the Image Quality of StyleGAN
https://github.com/NVlabs/stylegan2
```

```
@article{Karras2019stylegan2,
  title   = {Analyzing and Improving the Image Quality of {StyleGAN}},
  author  = {Tero Karras and Samuli Laine and Miika Aittala and Janne Hellsten and Jaakko Lehtinen and Timo Aila},
  journal = {CoRR},
  volume  = {abs/1912.04958},
  year    = {2019},
}
```

# Acknowledgements

The author would like to thank NVlabs, Tero Karras, Samuli Laine, Miika Aittala, Janne Hellsten, Jaakko Lehtinen, Timo Aila for providing StyleGan2 (https://github.com/NVlabs/stylegan2) and Joseph Paul Cohen and Paul Morrison and Lan Dao for providing the 'COVID-19 image data collection' dataset (https://github.com/ieee8023/covid-chestxray-dataset). 
