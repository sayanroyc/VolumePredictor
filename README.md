# Volume Predictor

### Dependencies
- MongoDB
	- A local database will hold the set of materials used for training the predictor
- Pymatgen, matminer
	- See handbook
- Python libs
    - ```sh
        $ conda create –name <env_name> python=2 numpy matplotlib pandas pymongo scipy scikit-learn plotly 
        ```
- Jupyter notebooks
	- ipyparallel – parallel processing 
    - jupyter_contrib_nbextensions – useful extensions (mostly code folding) (use pip install, not conda)


### Importing Materials Project data set
- setup
    - open (at least) two terminals, activate the python dev environment
    - ```sh
        $ source activate <env_name>
      ```
    - open a jupyter notebook
    - ```sh
        $ jupyter notebook
      ```
    - start mongodb instance
    - ```sh
        $ sudo mongod
      ```
- follow import_structures.ipynb
    - add Materials Project API key to api_key variable


### Running the Volume Predictor
- setup
    - open (at least) three terminals, activate the python dev environment
    - ```sh
        $ source activate <env_name>
      ```
    - open a jupyter notebook
    - ```sh
        $ jupyter notebook
      ```
    - start mongodb instance
    - ```sh
        $ sudo mongod
      ```
    - start the parallel processing engines
    - ```sh
        $ ipcluster start
      ```
- running
    - run all the cells under imports and functions
    - run the MAIN section
        - can either initialize everything or import from own data set
            - see section under functions to import previous data
    - remember to set the following before each run – this allows you to take breaks and analyze the data in between runs
        - init_iter
        - num_iter
        - percent_bonds_to_change_per_iter
        - weight_decay_per_iter
        - collection = db.materials_project (or db.mp_test)
- analysis
    - see analysis functions
        - display_bond_data(bond_name)
        - display_material_data(mat_name)