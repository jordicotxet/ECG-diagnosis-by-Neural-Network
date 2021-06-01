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



## Extended Sources
```
@article{ribeiro_automatic_2020,
title = {Automatic Diagnosis of the 12-Lead {{ECG}} Using a Deep Neural Network},
author = {Ribeiro, Ant{\^o}nio H. and Ribeiro, Manoel Horta and Paix{\~a}o, Gabriela M. M. and Oliveira, Derick M. and Gomes, Paulo R. and Canazart, J{\'e}ssica A. and Ferreira, Milton P. S. and Andersson, Carl R. and Macfarlane, Peter W. and Meira Jr., Wagner and Sch{\"o}n, Thomas B. and Ribeiro, Antonio Luiz P.},
year = {2020},
volume = {11},
pages = {1760},
doi = {https://doi.org/10.1038/s41467-020-15432-4},
journal = {Nature Communications},
number = {1}
}
```

``` 
@article{Strodthoff:2020Deep,
doi = {10.1109/jbhi.2020.3022989},
url = {https://doi.org/10.1109/jbhi.2020.3022989},
year = {2021},
volume={25},
number={5},
pages={1519-1528},
publisher = {Institute of Electrical and Electronics Engineers ({IEEE})},
author = {Nils Strodthoff and Patrick Wagner and Tobias Schaeffter and Wojciech Samek},
title = {Deep Learning for {ECG} Analysis: Benchmarks and Insights from {PTB}-{XL}},
journal = {{IEEE} Journal of Biomedical and Health Informatics}
}
```  
PTB dataset comes from:  
```
@article{Wagner:2020PTBXL,
doi = {10.1038/s41597-020-0495-6},
url = {https://doi.org/10.1038/s41597-020-0495-6},
year = {2020},
publisher = {Springer Science and Business Media {LLC}},
volume = {7},
number = {1},
pages = {154},
author = {Patrick Wagner and Nils Strodthoff and Ralf-Dieter Bousseljot and Dieter Kreiseler and Fatima I. Lunze and Wojciech Samek and Tobias Schaeffter},
title = {{PTB}-{XL},  a large publicly available electrocardiography dataset},
journal = {Scientific Data}
}

@misc{Wagner2020:ptbxlphysionet,
title={{PTB-XL, a large publicly available electrocardiography dataset}},
author={Patrick Wagner and Nils Strodthoff and Ralf-Dieter Bousseljot and Wojciech Samek and Tobias Schaeffter},
doi={10.13026/qgmg-0d46},
year={2020},
journal={PhysioNet}
}

@article{Goldberger2020:physionet,
author = {Ary L. Goldberger  and Luis A. N. Amaral  and Leon Glass  and Jeffrey M. Hausdorff  and Plamen Ch. Ivanov  and Roger G. Mark  and Joseph E. Mietus  and George B. Moody  and Chung-Kang Peng  and H. Eugene Stanley },
title = {{PhysioBank, PhysioToolkit, and PhysioNet}},
journal = {Circulation},
volume = {101},
number = {23},
pages = {e215-e220},
year = {2000},
doi = {10.1161/01.CIR.101.23.e215}
}
```



