# Mask R-CNN for Bacterial Cells Detection, Segmentation, and Size Distribution of Individual Cells


The repository includes:
* Source code of Mask R-CNN built on FPN and ResNet101.
* Training code for Biofilm dataset
* Pre-trained weights for MS COCO
* Pre-trained weights for Cells
* Jupyter notebooks to visualize the detection bacterial cells



# Getting Started
* [Test_cells.ipynb] It includes code to run object detection, instance segmentation, and size distribution of individual cells on arbitrary images.

* ([model.py](mrcnn/model.py), [utils.py](mrcnn/utils.py), [config.py](mrcnn/config.py)): These files contain the main Mask RCNN implementation. 

* [inspect_cells_model.ipynb] This notebook goes in depth into the steps performed to detect and segment objects. It provides visualizations of every step of the pipeline.


# Training on Cells dataset
We're providing pre-trained weights for Cells dataset. You can
use those weights as a starting point to train your own variation on the network.
Training and evaluation code is in `Cells.py`. You can import this
and you can run it directly from the command line as such:

```
# Train a new model starting from pre-trained COCO weights
python Cells.py train --dataset=/path/to/dataset --weights=coco

# Continue training a model that you had trained earlier
python Cells.py train --dataset=/path/to/dataset --model=/path/to/weights.h5

# Continue training the last model you trained. This will find
# the last trained weights in the model directory.
python Cells.py train --dataset=/path/to/dataset --model=last
```

The training schedule, learning rate, and other parameters should be set in `Cells.py`


## Requirements
Python 3.4, TensorFlow 1.3, Keras 2.0.8 and other common packages listed in `requirements.txt`.


## Installation
1. Clone this repository
2. Install dependencies
   ```bash
   pip3 install -r requirements.txt
   ```
3. Run setup from the repository root directory
    ```bash
    python3 setup.py install
    ``` 
    
## If you like our work and find useful, please cite as:

@article{ragi2021artificial,
  title={Artificial intelligence-driven image analysis of bacterial cells and biofilms},
  author={Ragi, Shankarachary and Rahman, Md Hafizur and Duckworth, Jamison and Kalimuthu, Jawaharraj and Chundi, Parvathi and Gadhamshetty, Venkataramana},
  journal={IEEE/ACM transactions on computational biology and bioinformatics},
  year={2021},
  publisher={IEEE}
}

