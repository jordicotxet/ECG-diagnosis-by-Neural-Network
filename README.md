# ECG-diagnosis-by-Neural-Network
This repository is created in order to re-perform the stats of Ribeiro's article. The second objective is to predict on the PTB-XL dataset using transfer-learning with Ribeiro's Neural Network pre-trained architecture.  
Then, the only training takes place with 3 Dense Layers added to the Main Model. Those 3 new layers are trained on 20 000 ECG, using 18 000 for training and 2 000 for validating  
## Citation
Please, before looking at this github look at those two works that inspired this project.  
  
>Ribeiro, A.H., Ribeiro, M.H., Paixão, G.M.M. et al. Automatic diagnosis of the 12-lead ECG using a deep neural network.
Nat Commun 11, 1760 (2020). https://doi.org/10.1038/s41467-020-15432-4  
  
>Wagner, P., Strodthoff, N., Bousseljot, RD. et al. PTB-XL, a large publicly available electrocardiography dataset. Sci Data 7, 154 (2020). https://doi.org/10.1038/s41597-020-0495-6  

## Requirements
This code was tested on `Python 3` with `Tensorflow 2.2`. There is an older branch (tensorflow-v1) that contain the code implementation for `Tensorflow 1.15`.  
You also need `wfdb` and `opencv` to process data from PTB-XL.  
You can install the dependencies directly by creating a conda environment.
``` 
conda env create -f ecg_env.yml
conda activate ecg_env
``` 
## New Model
The new model is watchable on this repos with the document `model.png`.     
Ribeiro's pre-trained model is available in: https://doi.org/10.5281/zenodo.3625017  
PTB-XL Dataset is available in: https://doi.org/10.13026/x4td-x982  
Finally, the big Ribeiro's dataset is available directly by contacting the `Telehealth Network of Minas Gerais`.

## Performances  


