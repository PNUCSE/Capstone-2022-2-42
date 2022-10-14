# SSD performance improvement through deep learning-based workload analysis

## Project introduction
<b>Solid State Drives</b> (SSDs) are nonvolatile storage devices with faster input/output, lower power, lower noise, and lower weight than traditional hard disk drives (HDDs). However, because the memory is made of NAND flash memory, it is impossible to write or overwrite data in place. The erase process must be completed before proceeding with a new write. At the moment, writing is done in pages, but erasure is done in blocks, which causes problems. If a new write is performed on the same address where a previous write was performed, the page written on the existing block becomes invalid. The writing then continues to an empty page in the block. When the number of blocks with empty pages falls below a certain threshold, <b>Garbage Collection</b> (GC) is performed to erase the block in which all pages are written. All valid data remaining in the block is written to an empty block during the erase operation, and all pages of that block are erased. This results in additional writing, which requires additional execution time. 

Our "Bros" team worked on improving SSD performance with a deep learning model. Using Stacked-LSTM model, our team was able to increase WA improvement by 9.86%. We tried different models on different hyperparameters to get the better result.

## Team introduction

#### 최성찬
* Email: sungchan3100@gmail.com, sungchan3100@pusan.ac.kr
* Student number: 201824641
* Role: team leader
  - Labeling data clustering
  - Simulator creation and testing
  - WA improvement measurement

#### Odgerel Ariunbold
* Email: odgerelariunbold719@gmail.com, odgerelariunbold@pusan.ac.kr
* Student number: 201824623
* Role: team member 
  - Hyperparameter tuning
  - Model training and improvement
  - Data analysis

#### Ganchuluun Narantsatsralt
* Email: tsatsralt2000@gmail.com, tsatsralt2000@pusan.ac.kr
* Student number: 201824621
* Role: team member
  - Preprocessing of learning data
  - Model design and development
  - Model training and evaluation

## Composition chart

![image](https://user-images.githubusercontent.com/115723043/195658439-8393a8b0-ba13-46ac-a066-cf8f93f77b6e.png)
<div align="center">
  <p> Research Object diagram </p>
</div>

![image](https://user-images.githubusercontent.com/115723043/195658404-26ade6a7-19e4-479d-808b-e6cdc936f800.png)
<div align="center">
  <p> Model Design </p>
</div>

## introduction and demonstration video

## How to use

##### Model usage
- The model directory includes our model's code. When we did the hyperparameter tuning, we used codes to change parameters.
- Saved model directory stores our models. We can use those models to check the results or evaluate the model.

```data``` folder contains the data to train. 

  ```data/traceProcess``` is a script to process whole data from ssdtrace-00 to ssdtrace-26 at once

  ```data/labeling``` folder contains the labeled data and codes to lable the datas.

  ```data/labeling/Sector.cpp``` is a code to calculate frequency, access interval, and overall i/o size.

```src/``` only source codes must be included in the subfolder of ```src```   

```src/greedyGC``` Garbage Collection algorithm implementation ```src```

```src/model``` Deep learning models

```src/model/cpp``` Deployment of LSTM Model to C++ environment. 


To load saved model
```
tf.keras.models.load_model(<The path of folder>)
```

Following code to unzip the file
```
!gzip -d <file path>
```
