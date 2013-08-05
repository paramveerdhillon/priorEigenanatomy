priorEigenanatomy
=================

A reproducible example of prior based eigenanatomy.

cd to "data" directory and then run the following command line to run p-Eigen.


sccan --svd prior[faces.mhd,face_mask.nii.gz,listPrior.txt,0.95,0.0] -n 10 -o faces.nii.gz  --PClusterThresh 100 -i 3 --l1 0.5


It assumes that ANTs is installed.

1).  faces.mhd--it is the data matrix where "n" is e.g. the number of patients and "p" is the number of voxels.

2).  face_mask.nii.gz- The image mask.

3).  listPrior.txt- A text file containing the list of priors (ROIs e.g. anatomical brain regions (one region per file)).

4).  0.95, parameter to control the tradeoff between influence of data and prior; higher values indicate higher influence of prior. In other words, the deformed ROIs will be close to the initial ROIs.

5).  0.0, The amount of sparsity in the final deformed ROIs (between 0 and 1), smaller values indicate more sparsity. Sparsity of "0.0" indicates that the sparsity will be chosen automatically in a totally data driven way from the input ROIs.

6). -n, indicates the number of priors (ROIs). 

7). -o, indicates the name of the output file.

8). --PClusterThresh: Cluster threshold as in VBM i.e. segregated regions in the output which are smaller than this size will be removed.

9). -i, -l1, the number of iterations and the l1 sparsity. The values given above are reasonable values and you might not want to change them.

