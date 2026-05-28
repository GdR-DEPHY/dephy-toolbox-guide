# Install objects

For now, objects can only be cloned and installed manually

```shell
git clone https://gitlab.com/tropics/objects
export PYTHONPATH=$PWD/objects/src:$PYTHONPATH
```

Python packages might need to be installed:

```shell
python -m venv $HOME/.local/pyenvs/objects
source $HOME/.local/pyenvs/objects/bin/activate
pip install scikit-image netCDF4 matplotlib
```

## On spirit

### Install your own version

```shell
# get project 
git clone https://gitlab.com/tropics/objects

# install dependencies 
module load python/meso-3.10 # => only this is spirit-specific 
python -m venv $HOME/.local/pyenvs/objects
source $HOME/.local/pyenvs/objects/bin/activate
pip install scikit-image netCDF4 matplotlib

# create profile
cat << EOD > $HOME/.local/etc/objects.profile
source $HOME/.local/pyenvs/objects/bin/activate
export PYTHONPATH=$PWD/objects/src:$PYTHONPATH
EOD
```

To use objects in a new terminal, always setup your environment first with: 

```shell
source $HOME/.local/etc/objects.profile
```

### Use a pre-installed version

On spirit, a pre-installed environment can be used with:

```shell
source /home/nvillefranque/swork/dephy/objects.profile
```

## Test 

Use scripts in the ```objects/example``` repo for testing, or open a python
console in your terminal and try:

```python
from identification_methods import identify
help(identify)
```

This should print a description of the identify function and exit.

You can also try a basic test case :

```python
from identification_methods import identify

ncdfFile = "/home/nvillefranque/swork/dephy/data/R25mL25km.ARMCU.OUT.LT1400.nc" # or your own data file here

listVarNames = ['RCT'] # list of relevant variables.

def cloudMask(dictVars) :
    rc = dictVars['RCT']
    mask=rc*0.   # same shape as RCT
    mask[rc>0]=1 # cell is in cloud if liquid water mixing ratio is positive
    return(mask)

clouds, _ = identify(ncdfFile, listVarNames, cloudMask, name="bench_cloud", write=False, overwrite=True)
print(clouds)
```
