# autoseg_container_boilerplate

The boilerplate example code in this repository can be used for adapting home-brewed deep learning models for use with the CERR Auto-Segmentation Pipeline.

Please note: for optimal compatibility with the wrappers enclosed here, we suggest providing Python requirements compatible with miniconda3.

The main components to assemble a pipeline container for use with CERR:
  1. Python wrapper: The script which processes the input imaging data (as prepared by CERR pipeline in H5 format) using the custom network model. 
  2. Singularity container recipe script (`sing_boilerplate`): Creates the virtualized Singularity container for running the process. The container bundles the model Python wrapper and additional dependencies. The wrapper is invoked by the container as defined by the command in the `%%app` section of the recipe. See script comments for full usage info.
  3. `model_wrapper`: Folder that house the Python wrapper (1) and additional Python scripts/modules as needed by the routine
  4. `model`: Folder containing the trained network weights for running the model
  
### CERR wiki links
* [Auto-Segmentation models](https://github.com/cerr/CERR/wiki/Auto-Segmentation-models)
  
### Singularity Docmentation
* [v3.5 User Guide](https://sylabs.io/guides/3.5/user-guide/)
* [FAQ](https://sylabs.io/singularity/faq/)

### References: 
* Aditya P. Apte, Aditi Iyer, Maria Thor, Rutu Pandya, Rabia Haq, Jue Jiang, Eve LoCastro, Amita Shukla-Dave, Nishanth Sasankan, Ying Xiao, Yu-Chi Hu, Sharif Elguindi, Harini Veeraraghavan, Jung Hun Oh, Andrew Jackson, Joseph O. Deasy, Library of deep-learning image segmentation and outcomes model-implementations, Physica Medica, Volume 73, 2020, Pages 190-196, ISSN 1120-1797, https://doi.org/10.1016/j.ejmp.2020.04.011.
