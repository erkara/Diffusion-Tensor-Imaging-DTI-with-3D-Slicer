# Diffusion-Tensor-Imaging-DTI-with-3D-Slicer
In this repo, you can find some of my works about diffusion tensor imaging using 3D Slicer.  The data set can be found at

https://spujol.github.io/NeurosurgicalPlanningTutorial/

This is the main ingredient of our paper about the efficacy and toxicity of drug transport on solid
tumors, which is to appear in in Pyhsical Review E. Access at 
https://journals.aps.org/pre/accepted/3d072RdaA1f15b1bd78c6860715e4f0dd1104b4c5

I am planning to provide a seperate file to describe how to process DTI data in the future. For now, summary of the folders in this repor is as follows;

DTICleaned

In theory, the diffusion tensor is symmetric and positive definite (SPD) but in practice the positive definiteness can be corrupted due to measurement noise. 
Thus we first re-sample the DTI volume to correct the tensors that are not positive semi-definite. "ResampledDTI.nhdr" in this folder is the noise-free
DTI volume on which we perform several post-processing operations. We can export several scalar measurements such as linear 
isotropy, axial diffusivity, spherical isotropy using this volume. 

DTI_Scalar_Measurements

DTI data is usually illustrated by condensing the tensor information into a scalar quantity or plotted as a color encoded texture map. 
The former consists of scalar measurements to quantify the magnitude or the shape of the diffusion. In terms of magnitude, mean diffusivity (MD), which is the mean of the eigenvalues of
the diffusion tensor, is one of the most common scalar measurements. On the other hand, fractional anisotropy (FA), which is the normalized variance of the eigenvalues, is the most
commonly used anisotropy measure. In addition to various scalar measurements, one can also consider the direction of the major eigenvector (the eigenvector associated with the largest
eigenvalue) and create a color map for the corresponding directions. The most commonly used color scheme in terms of anatomical planes is as follows; blue is superior-inferior, red
is left-right, and green is anterior-posterior. In this folder, you can see the visuluazitions of these scalar measurements.

Tumor_Segmentation

Here, we perform an image segmentation on the original DTI volume to segment the approximate GBM region. 

WhiteMatterExplorationData

This folder includes the original DTI data of a 35-year old male diagnosed with glioblastoma multiform (GBM). 
