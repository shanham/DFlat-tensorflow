# DFlat-tensorflow V4
 ### Note: DFlat is moving to Pytorch (<a href="https://github.com/DeanHazineh/DFlat-pytorch" target="_blank">DFlat-pytorch</a>). While the tensorflow version will remain open, long-term support, functionality improvements, and QOL updates will eventually only be provided for the pytorch version of the software.
<div align="center">
  <img src=/docs/imgs/DFlat_Long.png alt="Dflat" width="500"/>
</div>
<div align="center">
  <img src=/docs/imgs/autoGDS_metalens.png alt="Dflat" width="500"/>
</div>

# An End-to-End Design Framework for Diffractive Optics and Metasurface-Based Vision Systems
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

`D-Flat` is an auto-differentiable design framework for flat optics, specially geared to the design of dielectric metasurfaces for imaging and sensing tasks. This package was officially released alongside our paper,  <a href="https://deanhazineh.github.io/publications/Multi_Image_Synthesis/MIS_Home.html" target="_blank"> Polarization Multi-Image Synthesis with Birefringent Metasurfaces</a>, published in the proceedings of the 2023 IEEE International Conference of Computational Photography (ICCP). This package is further documented and discussed in the manuscript available on <a href="https://arxiv.org/abs/2207.14780" target="_blank">arxiv</a>. If you use this package, please cite the ICCP paper (See below for details). 

D-Flat provides users with:
- A validated, auto-differentiable framework for optical field propagation and rendering built on tensorflow Keras
- Pre-trained, efficient neural models to describe the optical response of metasurface cells
- An auto-differentiable field solver (RCWA) packaged as a TF-Keras layer that is easy to use

By treating optical layers in the same fashion as standard, differentiable neural layers, deep learning pipelines can be built to simultaneously optimize optical hardware and ML computational back-ends for the next generation of computational imaging devices.

## Version Notes 
Dflat version 4 presents several changes relative to v3. Some scripts in the Fourier layer have been modified to improve the computational speed and efficiency. The package has also been restructured for easier interpretability; we have removed extra scripts, functions, and files that were related to the original papers and were only there for initial academic benchmarking. Lastly, all data files are now stored on dropbox and downloaded during install.

Older versions will now be kept as seperate branches for archival purposes. 

Some of these changes might have introduced unexpected bugs or behaviors. Please report if you find something incorrect or errors in runtime.

## Usage and Documentation:

A readthedocs page will be provided in the future. You may also visit the code pages for projects that use DFlat to learn more (example: https://github.com/DeanHazineh/Multi-Image-Synthesis). Several tutorial notebooks (google collabs linked below) are also provided as demos. Additional examples will be provided in the future and we welcome community made examples sent by email.

For developers and researchers,
- a script to train neural models can be found in `DFlat/dflat/neural_optical_layer/core/trainer_models.py`
- a script to build a cell library using RCWA_TF can be found in `DFlat/dflat/cell_library_generation/`.

### (a) install and run DFlat in Google collab:

Note that DFlat can be easily installed and used in the cloud on Google Collab if desired. This is a potential solution for mac users who wish to use the code without access to a windows/linux compute cluster,  as tensorflow_gpu is not supported by mac.
Google collab versions of current examples can be found in the examples folder and online at the links:
- <a href="https://colab.research.google.com/drive/1MknLVB6cQ1GQ2xRfHhlAfCQPiWXLHUM3?usp=sharing" target="_blank">Tutorial_I_Dflat_Field_Propagation</a>
- <a href="https://colab.research.google.com/drive/162Fg0P_QGiddUUeXUrJhikAdy2qpNXpc?usp=sharing" target="_blank">Tutorial_I_RCWA_and_Physical_Layers</a>
- <a href="https://colab.research.google.com/drive/1a27zLKMXfObyjQDF5nWZ9ug-7jWzmQer?usp=sharing" target="_blank">Tutorial_I_Dflat_Library_and_Neural_Models </a>
- <a href="https://colab.research.google.com/drive/1uGNU0PsCUunibnkyLZUnGa4Y54vj6XZ3?usp=sharing" target="_blank">Demo_optimize_broadband_rcwa_metalens</a>
- <a href="https://colab.research.google.com/drive/1F2KR87CHTBnMHkAHDb04F3FBHE0iUueV?usp=sharing" target="_blank">Demo_optimize_monochromatic_neural_metalens</a>
- <a href="https://colab.research.google.com/drive/1an1HWkMf0ynw0F1YZx5s82pKVwxw2E0X?usp=sharing" target="_blank">Demo_optimize_dual_polarization_hologram</a>

### (b) install and run locally:

Install the local repository to your venv by entering the following in terminal:
```
git clone https://github.com/DeanHazineh/DFlat
pip install .
```
If there are unexpected issues with the pip install, try to install the package via: `python setup.py install`. This was needed on google collab but not for local builds for some unknown reason. 

## Future Notes:

- Please note that Tensorflow v2.10 is the last official tensorflow release with native GPU compatibility for Windows OS. DFlat is currently kept on v2.10 and will likely not be upgraded officially.
- Importantly, we are porting the package to Pytorch which has now become the dominant ML framework. Dflat-tensorflow will then no longer be updated and new developments will be released on DFlat-pytorch.
- We expect that the pytorch version will be both faster due to improvements to the back-end and easier to use

## Credits and Acknowledgements:
If you utilize DFlat or included data sets for your own work, please cite it by copying:

```
@INPROCEEDINGS{10233735,
  author={Hazineh, Dean and Lim, Soon Wei Daniel and Guo, Qi and Capasso, Federico and Zickler, Todd},
  booktitle={2023 IEEE International Conference on Computational Photography (ICCP)}, 
  title={Polarization Multi-Image Synthesis with Birefringent Metasurfaces}, 
  year={2023},
  pages={1-12},
  doi={10.1109/ICCP56744.2023.10233735}}
```

This work pulls inspiration from, builds on, or otherwise ports/modifies previous open-source contributions from the following individuals:
 * Shane Colburn - RCWA_TF
 * Manuel Guizar-Sicairos and Julio C. Guitierrez-Vega - Pyhank
 
## Contact:
This repository is intended to be accessible and community driven. It may not be fully error-proof.
If you have improvements, fixes, or contributions, please branch and initiate a merge request to master (or email me)!

For any questions, functionality requests, or other concerns, don't hesitate to contact me at dhazineh@g.harvard.edu. 

