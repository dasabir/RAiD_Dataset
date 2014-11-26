RAiD_Dataset
============

Re-Identification Across Indoor-Outdoor Dataset (RAiD) - Introduced in the work "Consistent Re-identification in a Camera Network" (ECCV 2014)

The dataset was collected at the Winstun Chung Hall of UC Riverside. It is a 4 camera dataset with 2 indoor and 2 outdoor cameras. The cameras are numbered as 1,2,3 and 4 where cameras 1 and 2 are indoor while cameras 3 and 4 are outdoor. 43 people walked in these camera views resulting in 6920 images. Among the 43 persons 41 people appeared in all the 4 cmareas where as person 8 is not present in camera 3 and person 34 is not present in camera 4.
A fully annotated mat file is provided in this dataset which contains a structure named 'dataset'. The important fields of the struct are described in detail below.
dataset.images - A 4-D matrix of size 128x64x3x6920 which contains the detections (RGB values in the 3 channels) resized to 128x64.
dataset.masks - A 3-D binary matrix of size 128x64x6920 which contains the foreground masks of the above detections.
dataset.cam - A 6920 length vector where each element gives the camera number to which the corresponding detection belong to. For example dataset.cam(70) is the camera number to which dataset.images(:,:,:,70) (and also dataset.masks(:,:,:,70)) belong to.
dataset.personID - A 6920 length vector where each element gives the person id of the corresponding detection. For example dataset.personID(70) is the person ID of the detection dataset.images(:,:,:,70) (and also dataset.masks(:,:,:,70)).
dataset.personSubsetImageIndex - A 6920 length vector where each element gives the detection number corresponding to a particular camera and person ID. For example dataset.cam(70) = 1, dataset.personID(70) = 2 and dataset.personSubsetImageIndex(70) = 20. This means the 70th image corresponds to the 20th detection of person 2 in camera 1.
dataset.count - Gives the total number of detections across all cameras.
dataset.peopleCount - Gives the total number of unique persons present in the dataset.
dataset.name - The name of the dataset.
