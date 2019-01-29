# DNA to DNA autoencoder

___

### Requirements

To run this demo you need `pyhton >= 3.0` (Anaconda distribution) together with `Jupyter Notebook/Lab` (Lab is preferred) to be installed on your machine, as well as all dependencies described in the `requirements.txt` file.

1) Install Ananconda following the instrucrions here: https://www.anaconda.com/download/. **Note**: After the installation is finished, make sure that the Anaconda path is added to your PATH.

2) Install Jupyter Lab and all dependencies.

On **MacOS / Ubuntu** you can run:
```
$ make install
```

3) To launch the application, run:
```
$ jupyter lab
```
and open the file `DNA_to_DNA.ipynb`.

### Data

The data is stored in the `hta2.txt` file. It is represented as a matrix with the expression levels of 32 genes (columns) over 20033 experiments (rows). 

### Model

The neural network is a simple **autoencoder** with 5 layers:

- an input layer
- a Lambda layer to transform the input data
- a hidden layer (the vector embedding) consisting of 16 neurons with ReLu activation
- a hidden layer with 32 neurons and Sigmoid activation
- a Lambda output layer to transfrom the data back to the desired format

It is trained for 100 epochs using the `RMSProp` oprtimizer and two possible evaluation metrics, described in the notebook.
