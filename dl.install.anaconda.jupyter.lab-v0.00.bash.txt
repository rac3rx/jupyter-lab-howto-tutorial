#
# Jupyter Lab HOWTO 
#

# go home
cd ~

# download anaconda; change what anaconda version you want at: https://repo.continuum.io/archive/
curl -Ok https://repo.continuum.io/archive/Anaconda2-5.2.0-Linux-x86.sh &&

# check hash
sha=$(sha256sum Anaconda2-5.2.0-Linux-x86.sh | cut -f1 -d' ') &&
[ "$sha" = "758e172a824f467ea6b55d3d076c132f" ] &&

# install anaconda
bash Anaconda2-5.2.0-Linux-x86.sh -b -p ~/anaconda &&
rm Anaconda2-5.2.0-Linux-x86.sh

cp ~/.bash_profile ~/.bash_profile.000
echo 'export PATH="~/anaconda/bin:$PATH"' >> ~/.bash_profile 

# Refresh basically
source .bash_profile

conda update conda
conda update anaconda
conda install -c conda-forge jupyterlab

# REF:
# https://gist.github.com/mGalarnyk



