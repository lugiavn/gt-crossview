# GT-CrossView
This contains the data and model for training crossview image ranking method described in:
Localizing and Orienting Street Views Using Overhead Imagery, ECCV 2016.
http://www.cc.gatech.edu/~nvo9/crossview_eccv2016/

## Data
Download from https://www.mediafire.com/folder/f4gga3h86d659/GTCrossView and unzip them into gt-crossview/data/

## Caffe model
You will need to install caffe with our proposed DBL log loss function:
https://github.com/lugiavn/caffe/tree/embedding_losses

## Note
Note that both data and the model is not the exact same one we used in the paper.

For data, we used the original high resolution images and resized them, making the entire dataset smaller so that it's easy to download and experiment with.
For the caffe model, we reimplemented/refactored the original code so that it's clean. Therefore the number might be different from the paper; if you train and test the model on the data here for comparison, the result would be:

| Tables               | Denver test set | Detroit test set | Seattle test set |
| -------------------- |:---------------:|:----------------:|:----------------:|
| Best classification  |                 |                  |                  |
| 1 rotation crop      |  93.0           |     89.5         |  89.4            |
| 4 rotation crops     |  93.4           |     89.9         |  89.8            |
| 16 rotation crops    |  93.7           |     90.1         |  89.9            |
| Recall at 0.01       |                 |                  |                  |
| 1 rotation crop      | 58.2            |    52.0          |  46.1            |
| 4 rotation crops     |  66.8           |     59.8         |  53.3            |
| 16 rotation crops    | 69.5            |     61.3         |  55.5            |

or you can use a model that we trained: https://github.com/lugiavn/gt-crossview/issues/1

