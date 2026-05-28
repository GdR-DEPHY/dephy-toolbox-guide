# DEPHY toolbox guide

## Getting started

Rejoindre le groupe mattermost [(lien d'invitation)](https://mattermost.lmd.ipsl.fr/signup_user_complete/?id=fgg1xo5qdp89tgwx1fe4h9qwrh&md=link&sbr=su) si ce n'est pas déjà fait

Pour anticiper au mieux ces ateliers nous vous proposons d'installer les
différents outils de la boite à out's de Dephy :

- dephy-scm pour travailler sur les cas 1D :
```shell
git clone http://github.com/GdR-DEPHY/DEPHY-SCM
```
- dephy-mnh pour générer des namelists mesonh :
```shell
git clone https://github.com/GdR-DEPHY/DEPHY-MNH
```

- High Tune Explorer pour le tuning: [more details in install-htexplo.md](./install-htexplo.md)
```shell
svn checkout http://svn.lmd.jussieu.fr/HighTune/trunk HighTune
```

- LMDZ [script-install.sh](https://lmdz.lmd.jussieu.fr/utilisateurs/guides/script-install.sh) :
```shell
wget http://lmdz.lmd.jussieu.fr/pub/install_lmdz.sh
bash install_lmdz.sh -name LMDZ -bench 0
cd LMDZ
wget http://lmdz.lmd.jussieu.fr/pub/1D/1D.tar.gz
tar xvf 1D.tar.gz
```

- Meso-NH ([mesonhv5.7](http://mesonh.aero.obs-mip.fr/mesonh57)) :
```shell
wget http://mesonh.aero.obs-mip.fr/mesonh/dir_open/dir_MESONH/MNH-V5-7-1.tar.gz
tar xvf MNH-V5-7-1.tar.gz
cd MNH-V5-7-1/src
export MNH_ECRAD=1
./configure
source ../conf/profile_mesonh
make
```

PHYEX la physique de Meso-NH et AROME externalisée :
```shell
git clone https://github.com/UMR-CNRM/PHYEX
./PHYEX/tools/INSTALL.sh --ALL --test
```

- ecrad pour le rayonnement :
```shell
git clone https://github.com/ecmwf-ifs/ecrad
```

- objects pour la détection d'objets : [more details in install-objects.md](./install-objects.md)
```shell
git clone https://gitlab.com/tropics/objects
```

