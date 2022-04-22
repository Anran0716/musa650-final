
## Landslide identification using machine learning with generative adversarial networks

Xiaoyi Wu, Anran Zheng

MUSA 650 preliminary report

### Introduction
Landslide is one common natural hazard, which happens frequently at mountainous places with high rainfall events and active geological activities. Machine learning and deep learning techniques have been proven to be an efficient and powerful tool in landslide prediction (Wang et al., 2021). Although several machine learning models, including SVM, RF and CNN, have been developed in landslide identification, few studies utilized generative adversarial networks(GAN) to address the imbalanced landslide inventories challenges (Al-Najjar el al., 2021). Under this context, this study performed GAN models on the spatial prediction of landslides in Hong Kong with comparison to several traditional machine learning models, such as RF, CNN, SVM and KNN. 

### Data
We choose Hong Kong as our study area because it often suffers from landslides and floods. The dataset is divided into two categories: landslide inventory and landslide conditioning factors. Landslide inventory is collected from Open Geo-Spatial Data in HK (2022), which includes 4183 historical landslide events. 10 conditioning factors are chosen as landslide conditioning factors and they can be divided into three types (see https://github.com/Anran0716/musa650-final/blob/main/rawdata/data.md for more details):
topological factors: elevation, slope, aspect and curvature. They are derived from 30m SRTM data gathered from Geospatial Data Cloud (2022). 
environmental factors:  distance to streamline (NextGIS), land use pattern (Open Geo-Spatial Data by Esri China) and NDVI (USGS).
geological factors: superficial geology.

After extracting these attributes from the data, we did data cleaning and processing to erase the null and extremely mistaken values. Besides landslide inventory that stands for positive sample in this study, negative samples were also extracted randomly from where no recorded landslide happened. Both the negative and the positive samples are the same size with 3741 samples respectively. ArcGIS Pro 2.9 software and Google Earth Engine were utilized in processing and preparing these data. 

### Methods 
The model input are 10 conditioning factors related to the occurence of landslide, the output is if the landslide is going to happen, and the measurement is the prediction accuracy, and the loss function is binary entropy loss function.
Firstly, data with 10 conditioning factors from Open Geo-Spatial Data in HK was split to 70：30 as training dataset and testing dataset. Then 4 machine learning models(RF, SVM, KNN) and 1 deep learning model(CNN) were utilized to predict the occurence of landslides. Generative adversarial network(GAN) was used to create synthetic data and increase training data size. Finally, the performance of the model with GAN and without GAN synthetic data was compared to evaluate the contribution of GAN in prediction. 

### Reference
H. Wang, L. Zhang, K. Yin, H. Luo and J. Li. Landslide identification using machine learning. Geoscience Frontiers 2021 Vol. 12 Issue 1 Pages 351-364. DOI: 10.1016/j.gsf.2020.02.012

H. A. H. Al-Najjar, B. Pradhan, R. Sarkar, G. Beydoun and A. Alamri. A New Integrated Approach for Landslide Data Balancing and Spatial Prediction Based on Generative Adversarial Networks (GAN). Remote Sensing 2021 Vol. 13 Issue 19. DOI: 10.3390/rs13194011

Open Geo-Spatial Data by Esri China (Hong Kong) Ltd. Retrieved April 7, 2022, from https://opendata.esrichina.hk/ 

Geospatial Data Cloud. Retrieved April 7, 2022, from http://www.gscloud.cn/

NextGIS. Retrieved April 7, 2022, from https://data.nextgis.com/en/

Survey, USGS. Earth explorer. Retrieved April 7, 2022, from https://earthexplorer.usgs.gov/


