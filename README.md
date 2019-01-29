# DNA to DNA autoencoder

___

### Requirements

To run this demo you need `pyhton >= 3.0` (Anaconda distribution) together with `Jupyter Notebook/Lab` (Lab is preferred) to be installed on your machine, as well as all dependencies described in the `requirements.txt` file.

1) Install Ananconda following the instrucrions here: https://www.anaconda.com/download/. **Note**: After the installation is finished, make sure that the Anaconda path is added to your PATH.

2) Install Jupyter Lab and all dependencies.

- On **MacOS / Ubuntu** you can run:
```
$ make install
```
- On other OS you need to install Jupyter Lab and all dependencies from the `requirements.txt` file.

3) To launch the application, run:
```
$ jupyter lab
```
and open the file `DNA_to_DNA.ipynb`.

---

### Data

The data is stored in the `hta2.txt` file. It is represented as a matrix with the expression levels of 32 genes (columns) over 20033 experiments (rows):
```
                 AN.387	AN.414	AN.451	AN.562	AN.596	...     ST.405	ST.449	ST.450	ST.667	ST.679
ENSG00000000003	 6.023	 6.031	 5.844	 7.663	 6.139	...     6.523	 7.011	 6.993	 6.536	 7.333
ENSG00000000005	 3.540	 3.397	 3.780	 3.758	 3.590	...     3.842	 3.737	 3.652	 3.793	 3.731
ENSG00000000419	 8.237	 8.108	 8.198	 8.175	 8.556	...     8.736	 8.359	 7.985	 8.634	 8.943
ENSG00000000457	 5.953	 6.146	 5.870	 5.899	 6.032	...     6.248	 5.655	 5.524	 5.821	 5.834
...
```

---

### Model

The neural network is a simple **autoencoder** with 5 layers:

- an input layer
- a Lambda layer to transform the input data
- a hidden layer (the vector embedding) consisting of 16 neurons with ReLu activation
- a hidden layer with 32 neurons and Sigmoid activation
- a Lambda output layer to transfrom the data back to the desired format

It is trained for 100 epochs using the `RMSProp` oprtimizer and two possible evaluation metrics, described in the notebook.
