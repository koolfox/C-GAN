**[Cross-Domain Face Synthesis using a Controllable GAN](https://arxiv.org/abs/1910.14247)**
===========

This page contains end-to-end demo code that generates a set of synthetic face images under a specified pose from an unconstrained 2D face image based on the information obtained from target domain.  

## Prerequisite

- **[Download the Basel Face Model](http://faces.cs.unibas.ch/bfm/main.php?nav=1-2&id=downloads)** and move `01_MorphableModel.mat` into the folders

## Instructions:
__Install:__
* keras
* tensorflow-gpu
* scipy 1.1.0
* scikit-image

```
sudo apt-add-repository ppa:zarquon42/meshlab
sudo apt-get update
sudo apt-get install meshlab=1.3.2+dfsg1-2build4
```


```
pip install git+https://www.github.com/keras-team/keras-contrib.git
```

__Generating 3D simulated images from still images:__

* Put the still images in "./face3d/input/", while each identity is in a seperate folder.
* Run:
```
pyhton face3d.py
```
* 3D rendered results will be in "face3d/output"


__Using CGAN to refine the 3D simulated images:__

Put the train and test 3D simulated data in:
```
./data/chokepoint/train_sim
./data/chokepoint/train_sim
```

Put the train and test target data in:
```
data/chokepoint/train_target
data/chokepoint/train_target

Put the test and train labels (only 3D simulated data needs label) in:
```
./data/chokepoint/test_sim_labels.txt
./data/chokepoint/train_sim_labels.txt
```

Run:

```
python cgan.py
```

Results will be in "./output"


```
## Data

- **[ChokePoint](http://arma.sourceforge.net/chokepoint/)** 
- **[COX-S2V](http://vipl.ict.ac.cn/view_database.php?id=3)** 



