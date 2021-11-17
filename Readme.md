# Liver Steatosis segmentation

This study aims to segment liver steatosis areas with a deep learning method derived from the mask-rcnn.

## About Datasets
All the images used in training and testing are in the same size, 1024X1024X3


## Files instruction
Three python files are included, `steatosis2.py`, `steatosis2_Predict.py` and `Filter_prediction_results.py`.

- The `steatosis2.py` is for training.
- The `steatosis2_Predict.py` is for prediction, which calls some of the functions from `Filter_prediction_results.py`.


## Folders instruction

1. logs: In the logs folder, the trained models are stored, namely, `mask_rcnn_steatosis_0049.h5`, `mask_rcnn_steatosis_0060.h5` and `mask_rcnn_steatosis_0069.h5`.
The number of 0049,0060,0069 means the trained epoch, the latest one is 0069.

2. mrcnn: In the mrcnn folder, the details of model architecture is built and some config information is required. The filename that has number 2 meaning the version, the larger the number is, the latest the version is. Normally, we will use the latest version, in this case, we use all files that contain number 2, that is `model2.py`, `visualize2.py`, while those with _Copy1 are the copy of corresponding files before revisions.  The `model2-Copy1.py` is for the steatosis prediction that takes testing cases stored in a folder rather than an image.

3. samples: In the folder samples, the prediction file are stored: `Filter_prediction_results-Copy1.py`,`steatosis2-Copy1.py`, `steatosis2_Prediction-Copy1.py`, `Filter_prediction_results-Copy2.py`, `steatosis2-Copy2.py`, `steatosis2_Prediction-Copy2.py`. Those files are some copies of prior code.


4. stage1_test, test_data_anywhere: The two folders are some testing data that can be used. They both for prediction of steatosis in folders.

## Configuration file:
1. In `Steatosis2_Predict.py`, the Predict function has some configurations, including the ##DEVICE##, you can set '/cpu:0' to run the code on cpu0, while set '/gpu:0' to run the code on gpu0. When we run detection, the ##TEST_MODE## is 'inference'. `steatosis2_Predict.py` calls the function  `predict() defined in the file.

2. In `Steatisis2.py`, there is a class named SteatosisConfig, which is for the steatosis class configuration and for the whole training process.There is also a SteatosisInferenceConfig class, mainly for inferencing. Details can be seen in the code.

## Reference
[Xiaoyuan Guo, Fusheng Wang, George Teodoro, Alton Farris, Jun Kong, “Liver Steatosis Segmentation with Deep Learning Methods,” IEEE International Symposium on Biomedical Imaging: From Nano to Macro (ISBI), pp.24-27, Venice, Italy, April 2019.](https://ieeexplore.ieee.org/document/8759600)
