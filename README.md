# tmap-instalation
Instructions for the installation of the R package tmap, starting on a clean install of Ubuntu 16.04 LTS

# After installing Ubuntu, on a terminal:
sudo apt-get update
sudo apt-get upgrade

# Instaltion of R
sudo echo "deb http://cran.rstudio.com/bin/linux/ubuntu xenial/" | sudo tee -a /etc/apt/sources.list
sudo apt-get update
sudo apt-get install r-base
sudo apt-get install r-base-dev 

# Instalation of Rstudioi
# download
https://download1.rstudio.org/rstudio-xenial-1.1.414-amd64.deb
# then install it using what you want, I used Ubuntu Software Center

# Installation of gdal
sudo apt-get install synaptic
# then install libgdal1-dev

# Instalation of Ubuntugis
# Add the next two lines to your /etc/apt/sources.list
deb     https://qgis.org/ubuntugis xenial main
deb-src https://qgis.org/ubuntugis xenial main
wget -O - https://qgis.org/downloads/qgis-2017.gpg.key | gpg --import
gpg --fingerprint CAEB3DC3BDF7FB45
gpg --export --armor CAEB3DC3BDF7FB45 | sudo apt-key add -
sudo apt-get update
sudo apt-get install qgis python-qgis qgis-plugin-grass
# it should return an error, so then
sudo add-apt-repository -y ppa:ubuntugis/ubuntugis-unstable
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install qgis python-qgis qgis-plugin-grass

gdalinfo --version

# Then, we are going to install the last libs for tmap package
sudo apt-get install libudunits2-dev
sudo apt-get install -y libprotobuf-dev protobuf-compiler
sudo add-apt-repository -y ppa:opencpu/jq
sudo apt-get update
sudo apt-get install libjq-dev
# (for other systems try install libjq-dev)
#Finally install libv8-3.14-dev from synaptic

# Then inside R
install.packages("tmap")
