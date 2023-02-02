# tesseract-train

This is a training dataset for Tesseract

First install tesseract trainer:

sudo apt-get update -y

sudo apt-get install -y libtiff-dev

sudo apt-get install -y libpng-dev

#remove previous versions
sudo apt-get autoremove -y tesseract-ocr

#download the repository: https://github.com/tesseract-ocr/tesstrain
#enter inside and change his permissions:
sudo chmod -R o+rwx *

sudo apt-get install dos2unix

sudo make leptonica tesseract
sudo make tesseract-langdata

#This install will set the trained data path to the: /usr/share/tessdata/
#To run the tesseract you must download the trained-best lang "por" files 
#on https://github.com/tesseract-ocr/tessdata_best
#to this directory: /usr/share/tessdata/

#Copy this training dataset on the /data diretory of the repository above
#follow the steps described in the repository: https://github.com/tesseract-ocr/tesstrain
#Example to make training:
sudo make training MODEL_NAME=por_cup START_MODEL=por PSM=7 TESSDATA=/usr/share/tessdata/

#The trained file will be done on the /data diretory of the repository
