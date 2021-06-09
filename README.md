# ECG-diagnosis-by-Neural-Network
This repository is created in order to re-perform the stats of Ribeiro's article. The second objective is to predict on the PTB-XL dataset using transfer-learning with Ribeiro's Neural Network pre-trained architecture.  
Then, the only training takes place with 1 Output layer added to the Main Model. This new layer is trained on 22 000 ECG, using 20 000 for training and 2 000 for validating  
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

## Description
To validate the stats using the Ribeiro's model on 30 000 ECG, look at `verif_data.ipynb`, you will see a recall level close to 100% and a pretty good precision rate.
To try using Transfer Learning on a new Dataset coming from PTB-XL, look at `Transfer_learning_PTB-XL.ipynb`. You can also find the plot of ECG after ResNet exposure and after interpolation.


## New Model
The new model is watchable on this repos with the document `model.png`.     
Ribeiro's pre-trained model is available in: https://doi.org/10.5281/zenodo.3625017  
PTB-XL Dataset is available in: https://doi.org/10.13026/x4td-x982  
Finally, the full Ribeiro's dataset is available directly by contacting the `Telehealth Network of Minas Gerais`.


## Performances  

Here are the scores of our transfer-learned model, to compare we have the `no-train` model that is just the Ribeiro's pre-trained model with the new output before training, the `part-train` refers to a model on which only the output layer is train and the other part is frozen, and the `full-train` is a model on which the full model is trained.  
![image](https://user-images.githubusercontent.com/83590513/121030645-f47a7a80-c7a9-11eb-8fc4-b906c8673852.png)  
*Binnary Accuracy corresponds to the percentage of correct prediction for each disease when accuracy means the percentage of correct prediction for the four diseases.  
Sensitivy, refers to the percentage of disease detected.*
  
We can easily see that the full train model is largely superior to the previous one, because the adaptation to this new dataset is better. However,  no optimizaton or bootstrapping have been used maybe that is why we do not have scores as good as it was on Ribeiro's dataset.
  
Concerning the training phase, here are few graphs provided by TensorBoard comparing the full-train and the part-train model on the Val_Loss and Val_Auc metrics.
### Validation loss
![image](https://user-images.githubusercontent.com/83590513/121031869-0a3c6f80-c7ab-11eb-8fa1-838707cfc258.png)  
### Validation AUC (area under the curve)
The area under a curve between two points can be found by doing a definite integral between the two points. To find the area under the curve y = f(x) between x = a and x = b, integrate y = f(x) between the limits of a and b. Areas under the x-axis will come out negative and areas above the x-axis will be positive. It represents the degree or measure of separability. It tells how much the model is capable of distinguishing between classes. Higher the AUC, the better the model is at predicting 0s as 0s and 1s as 1s.  
![image](https://user-images.githubusercontent.com/83590513/121032037-2f30e280-c7ab-11eb-8b20-ebe875dba6cd.png)
  
As we could expect those two graphs confirms that the full-trained model is really adaptated to this new problem while the part-train is not able to lear and we can see that the validation loss associated is quite stable...



  
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



