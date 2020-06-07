# Turbofan Warning System
DNN for predicting turbofan failure using [NASA Turbofan Simulation Dataset](https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/)
![](https://raw.githubusercontent.com/sfsy1/Turbofan_Predictor/master/visual.png)
#### Please refer to `.ipynb` and `.pdf` files for full details.

## Requirements
* Python 3.5+
* torch
* pandas
* Jupyter

## Methodology
### Model
A 2-layer DNN is used to predictor whether the engine is failing in the next 15 cycles. Windows of sensor measurements are fed into the DNN during training/inference. The intuition is that by feeding the model a window of data, it will learn to deal with the noise in the sensors. 

### Labels
Instead of using a binary label (1 for failing in the next 15 cycles; 0 for the rest), a smoother labelling system is used. Details in the jupyter notebook.

## Results
The predictor is generally warns of a failure in the next 15 cycle at around the 19th cycle before failure, with error of +-4 cycles. Depending on how you set the threshold, and define the costs of early and late warnings, the results can differ.
