# Install high tune explorer

bench.sh -> setup.sh -> lmdz1d


```shell
svn checkout http://svn.lmd.jussieu.fr/HighTune/trunk HighTune
cd ./HighTune
conda deactivate # mandatory 
module purge # mandatory 
# install High Tune Explorer and run a small tuning example
# -> outputs in ./WORK/EXEMPLE/
./setup.sh
```

```shell
# install LMDZ1D and run a small tuning example
# -> outputs in ./WORK/BENCHLMDZ/
./bench.sh
```


# MAC


Poblem on mac because -i is not working with sed but it is with gsed.

Could use gsed instead
```
brew install gsed
```
but `alias sed="gsed"` is not working in a script

Could be added in `~/.bash_aliases` but not very clean
```shell
shopt -s expand_aliases                                                           
source ~/.bash_aliases 
```
