# Exercise Session 3: Introduction to Instance Segmentation

## Connect to your HT Jupyter instance...


1. SSH into our cluster to enable port forwarding. The command is something like:

```
ssh your.user@hpclogin.fht.org -L 8888:gnodeXX:YYYY
```

Replace XX and YYYY, as well as insert your real user name.

2. Now connect to your Jupyter instance from your local broser by going to:
```
localhost:8888
```

## Clone this repo...

In Jupyter...

* Open a terminal window (inside the browser, from within Jupyter).
* Clone this repository by writing `git clone https://github.com/dl4mia/03_instance_segmentation`.
* Navigate into the new folder, containing the envorinment setup and the exercises  


## Setup Environment

From within the same terminal in your browser, create a `conda` environment for this exercise and activate it:


```
conda env create -f environment.yaml
```

Test whether tensorflow and stardist was properly installed and run the following in a fresh notebook:

```
import tensorflow as tf
import stardist 

print(tf.test.is_gpu_available())
res = tf.keras.layers.Conv2D(1,(3,3))(tf.zeros((1,100,100,1)))

```

Now navigate to the exercise folder we cloned just before and start with the exercises! 


## Exercises


In the folder you will find 3 different notebooks that demonstrate a DL based segmentation workflows of increasing complexity. Please also note the questions/exercises (<span style="background-color:lightblue">marked by blue back ground</span>) that you should discuss with your fellow course members.   

#### `1_semantic_segmentation_2D.ipynb` 

A simple *semantic* segmentation pipeline for 2D images using a good old UNet network. Always a good starting point and a solid baseline to compare against when using more fancy tools! 


#### `2_instance_segmentation_2D.ipynb.ipynb`

A *instance* segmentation pipeline for 2D images using a stardist 2D network. The data consists of fluorescently labeled nuclei, which are typically quite roundish thus rendering this approach suitable. 

### `3_instance_segmentation_3D.ipynb.ipynb`

A *instance* segmentation pipeline for 3D images using a stardist 3D network. The data consists of synthetically created nuclei.
