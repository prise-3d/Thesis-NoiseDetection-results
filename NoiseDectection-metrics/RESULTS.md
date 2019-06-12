# NoiseDetection-metrics

## Description
 
All results obtained from [NoiseDetection-metrics](https://github.com/prise-3d/Thesis-NoiseDetection-metrics.git) project in order to classify noisy or not noisy synthesis images obtained from monte carlo rendering process.

## Results

### 1.SV_with_SVM

#### Description

Study of all SV values obtained from SVD compression of images and trying to classify them (noisy/not noisy image).

#### Parameters
- Interval chosen from SV (begin and end)
- Number of components from SV
- Kind of normalization (3 differents way)
- Number of zones taken ramdomly in training set from the 16 available of an image
- The features used from pool of features computed from SV

#### Pool of features

- lab (Use of luminance canal obtained from Lab)
- mscn (Mean Substracted Coeffiecients Normalized)
- low_bits_2 (only 2 bits taken from from lab)
- low_bits_3 (only 3 bits taken from from lab)
- low_bits_4 (only 4 bits taken from from lab)
- low_bits_5 (only 5 bits taken from from lab)
- low_bits_6 (only 6 bits taken from from lab)
- low_bits_4_shifted_2 (only 4 bits shifted by 2 taken from from lab)

### 2.SV_Statistics

#### Description

Study of statistics obtained from SV vector obtained from SVD compression.

Computed statistics are:
- Mean
- Median
- Standard deviation
- Variance
- Percentile
- Area under SV curve

#### Parameters
- Kind of normalization (3 differents way)
- Number of zones taken ramdomly in training set from the 16 available of an image
- The features (here computed statistics) used from pool of features computed from SV

#### Pool of features

- sub_blocks_stats (all stats)
- sub_blocks_area (only area under curves from sub blocks)
- sub_blocks_stats_reduced 
- sub_blocks_area_normed

### 3.SV_Correlation

#### Description

Study of correlation (using pearson correlation coefficient) between each components of SV vector on the whole dataset (all scences data).

#### Parameters
- $n$, the number of highest or lowest correlated components to keep
- Kind of normalization (3 differents way)
- Number of zones taken ramdomly in training set from the 16 available of an image

#### Pool of features
- lab (Use of luminance canal obtained from Lab)
- mscn (Mean Substracted Coeffiecients Normalized)
- low_bits_2 (only 2 bits taken from from lab)
- low_bits_3 (only 3 bits taken from from lab)
- low_bits_4 (only 4 bits taken from from lab)
- low_bits_5 (only 5 bits taken from from lab)
- low_bits_6 (only 6 bits taken from from lab)
- low_bits_4_shifted_2 (only 4 bits shifted by 2 taken from from lab)

### 4.MSCN_stats

#### Description

Study of statistics on MSCN matrix obtained on synthesis image. Only variance is computed on sub blocks.

#### Parameters
  
- Kind of normalization (3 differents way)
- Number of zones taken ramdomly in training set from the 16 available of an image
  
#### Pool of features

Note that **mscn_var_$n$** is the number of sub blocks.

- mscn_var_4 
- mscn_var_16
- mscn_var_64
- mscn_var_16_max (data is sorted from max variance to min)
- mscn_var_64_max (data is sorted from max variance to min)
  

### 5.Data_separation

#### Description

Use of different way to train data:
- using all data
- using splited data from human threshold
- using only data close to human threshold

#### Parameters

- Kind of normalization (3 differents way)
- Number of zones taken ramdomly in training set from the 16 available of an image

#### Pool of features

- lab (Use of luminance canal obtained from Lab)
- mscn (Mean Substracted Coeffiecients Normalized)
- low_bits_2 (only 2 bits taken from from lab)
- low_bits_3 (only 3 bits taken from from lab)
- low_bits_4 (only 4 bits taken from from lab)
- low_bits_5 (only 5 bits taken from from lab)
- low_bits_6 (only 6 bits taken from from lab)
- low_bits_4_shifted_2 (only 4 bits shifted by 2 taken from from lab)
- ica_diff
- svd_trunc_diff
- ipca_diff
- svd_reconstruct
- highest_sv_std_filters (use of different filters on images and SVD computed on it)
- lowest_sv_std_filters (use of different filters on images and SVD computed on it)