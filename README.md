## Documentation for the codes used in the [publication]() submitted for review in the [XYZ journal]() by [Authors]() 
 
 ## Installation
 The usage of this package requires python package [vollseg](https://pypi.org/project/vollseg/) and     Fiji plugin [BTrack](https://imagej.net/plugins/btrack/). 
 ### VollSeg installation
 For installation of vollseg please see the instructions [here](https://github.com/Kapoorlabs-CAPED/VollSeg#installation). vollseg is also available as a Napari plugin and can be used instead of using it with the Jupyter notebooks, for installing vollseg as a Napari plugin please see [here](https://www.napari-hub.org/plugins/vollseg-napari).
 
 ### BTrack installation
 For installing the Fiji plugin [BTrack](https://imagej.net/plugins/btrack/) please visit it's ImageJ wiki page and follow these [instructions](https://imagej.net/plugins/btrack/#installation)
## Tissue Segmentation
 The tissue was imaged using transmitted light microscopy and its segmentation was challenging due to lack of background present in the images. To segment the tissue we created a training dataset of manually annotated tissue region and trained a [U-Net model](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/Segmentation/Tissue_segmentation_training.ipynb) using this notebook. We used a kernel size of 7 as the spatial variation in transmitted light images is much lower as compared to the fluorescently labelled images. The segmentation model prediction can be applied either using our [Colab notebook](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/Segmentation/Colab_Tissue_segmentation_prediction.ipynb) or local [jupyter notebook](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/Segmentation/Tissue_segmentation_prediction.ipynb).
## Tissue Branch Tracking
Post segmentation we created a customized tool in Fiji called [BTrack](https://imagej.net/plugins/btrack/) to track the growing ends of the tissue branches. The input to this plugin is the Raw image (to display the results of tracking) and the segmentation image (to perform the skeletonizaiton operation on).
## Tissue Track Analysis
Post tracking we perform the track analysis in python. We created tailored [jupyter notebooks](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/TrackAnalysis/BTrack_bud_analysis.ipynb) that take in the txt files generated by [BTrack](https://imagej.net/plugins/btrack/) and plot the velocity of all the tracks, their [statistical distribution](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/TrackAnalysis/BTrack_bud_statistics.ipynb) and also computes the mean velcotiy of growth for the whole experiment. After analyzing several experiment susing the tool we can then evaluate statistical significant differences between the different populations using the standardized T-test approach using [this notebook](https://github.com/Fre-Team-Curie/Embryo-mammary-gland/blob/main/TrackAnalysis/BTrack_Ttest.ipynb)
## Requirements

- Python 3.7 and above. Latest version of [Fiji](https://imagej.net/software/fiji/downloads).
 
## License

Under BSD 3 license. See [LICENSE](LICENSE).

## Authors

- [Claudia Carabana](https://imagej.net/people/claudiacarabana)
- [Varun Kapoor](https://imagej.net/people/kapoorlab) 
