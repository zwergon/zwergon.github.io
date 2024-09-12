# MDataset
Management of PostgreSQL database for RockNet and MetNet project. Versionnig of dataset. Create a Python package that takes VisionDataset standards to access RockNet and MetNet databaes


## Version of the Package
2.0.4 -> Download and load dataset using self made indexed binary format, checks are made to ensure integrity of the datasets before use.
      -> We load into memory only memory adresses in binary format, this method reduce greatly the need of RAM

# How to use the package
# For RockNet :
```
from dataset.rocknet import RockNet
```
```
train_dataset = RockNet(root='',type=DSType.TRAIN,transform=<set of transformation>,version='1.0 Test',download=True,host='10.25.11.36')
```
Here are the available options :
- --root is the place where you will store the dataset as pkl files
- --type = int choices=[0 for train, 1 for test and 2 for valid] 
- --transform = transform 
- --download bool
- --version_number = "" "0.0" by default, choices=["0.0","1.0"]
- --version_type = "" None by default,choices=["Premium","Premium Acceptable"]

If you want to access the "1.0" dataset you leave empty the version_type

# Description of the datasets

The datasets begining with 1.0 are dataset made with the datas of the folowing [images,metadatas] : '\\irfich3\R16-group\Projets\MPE_Offres_Digitales_CRRE\RockNet\Data\---- Bases de données vérifiées\2-DataSetFull_v2_trié_nettoyé -12 2023'
But without the lithologies on stand by

- "0.0" is dataset to test the code, you have one image of each classes for each train,test,valid

For the 3 following dataset the 70/20/10 repartition is made between Train,Test and Valid (randomly made)

- "1.0" is made of all images 

- "1.0 Premium" is made with only the Premium images

- "1.0 Premium Acceptable" is made with both Premium and Acceptable images

