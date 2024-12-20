# Sentinel-1 EW RTC (pyroSAR)

Notebook for creating Radiometrically Terrain Corrected (RTC) backscatter data for Sentinel-1 EW using the pyroSAR (SNAP backend) software. All inputs are downloaded in the notebook.

# SNAP Instructions

1. **Install SNAP**

Installers - https://step.esa.int/main/download/snap-download/ 

SNAP for linux can be installed from the command line. 

```sh

wget https://download.esa.int/step/snap/9.0/installers/esa-snap_sentinel_unix_9_0_0.sh

chmod 777 esa-snap_sentinel_unix_9_0_0.sh

sh esa-snap_sentinel_unix_9_0_0.sh -q esa-snap.varfile

export PATH="$PATH:$HOME/snap/bin"

sh update_snap.sh

rm esa-snap_sentinel_unix_9_0_0.sh

```


2. **Install miniconda (if a suitable conda envrionment not already installed)**

```sh
mkdir  -p  ~/miniconda3

wget  https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh  -O  ~/miniconda3/miniconda.sh

bash  ~/miniconda3/miniconda.sh  -b  -u  -p  ~/miniconda3

rm  -rf  ~/miniconda3/miniconda.sh

~/miniconda3/bin/conda init bash

```

3. **Create the conda envrionment**

```sh
conda env create -f environment.yml
```

4. **Activate the environment**

```sh
conda activate pyrosar_rtc
```

5. **Setup credentials**

* setup a nasa earthdata account at https://urs.earthdata.nasa.gov/users/new
* add credentials to **credentials/credentials_earthdata.yaml** based on example file in folder
* setup a ESA CDSE account at https://dataspace.copernicus.eu/
* add credentials to **credentials/copernicus_earthdata.yaml** based on example file in folder

6. **run the notebook**

# GAMMA Instructions

1. **Connect to the NCI**

You must have access to the following projects
- yp75
- dg9

It is useful to have access to the Copernicus Hub project (fj7) as well.

2. **Set up and activate conda environment**

See SNAP instructions above

3. **Create PyroSAR's GAMMA API**

cd to this repository, noting it is already located at 
`/g/data/yp75/projects/pyrosar_processing/s1-rtc-pyrosar-notebook`

Run `python initialise_gamma.py`

4. **Move scene to be processed to `data` folder.**

5. **Run the notebook**
