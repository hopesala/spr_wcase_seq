# spr_wcase_seq
As researchers, we firmly believe in the concept of reproducible research.

Thus, we release the codes of simulation, algorithm development, and testing online on GitHub for the paper "A robust star identification algorithm with star shortlisting" (<https://doi.org/10.1016/j.asr.2018.02.029>).

This repository contains the codes for simulation and testing of the star identification algorithm based on worst case patch mismatch and running sequential angular match technique which is proposed in the paper. 

Please cite our paper appropriately if you use these codes in your research for development, simulation or testing of a new star identification algorithm or comparison & benchmarking with the above-mentioned algorithm, We welcome any questions regarding the code.

This code is only for academic and research purposes. Commercial use of this code is not permitted.

Citation of the paper "A robust star identification algorithm with star shortlisting":

@article{mehta2018robust,<br />
  title={A robust star identification algorithm with star shortlisting},<br />
  author={Mehta, Deval Samirbhai and Chen, Shoushun and Low, Kay Soon},<br />
  journal={Advances in Space Research},<br />
  volume={61},<br />
  number={10},<br />
  pages={2647--2660},<br />
  year={2018},<br />
  publisher={Elsevier}<br />
}

## Repository details

This repository contains three folders. The information about each of the folder is described as below.

#### 1. simulate - Codes for simulating the star images
&nbsp;&nbsp;&nbsp;&nbsp; Convert_Axis_2_AttitudeMatrix.m -- For converting the ECI (Star position in the catalog) frame to the camera frame (Star sesnsor).<br />
&nbsp;&nbsp;&nbsp;&nbsp;Find_neighbor_star_FOV.m -- For finding the number and position of the neighboring stars in a specified FOV from the center star.<br />
&nbsp;&nbsp;&nbsp;&nbsp;PSF.m -- Point Spread Function simulation of the star amongst the pixels.<br />
&nbsp;&nbsp;&nbsp;&nbsp;Plot_sky_images.m -- For simulating the star images at a specific RA & DEC angle along with a defined FOV (this function is used by the Testing technique eventually).<br />
&nbsp;&nbsp;&nbsp;&nbsp;centroider.m -- Finding the centroid of the stars in the image.<br />
&nbsp;&nbsp;&nbsp;&nbsp;SKY2000_Magnitude6_doublestars_0.12.txt -- Star catalog (adopted from SAO) containing the star ID and it's corresponding RA, DEC and Mv information. Stars having a relative magnitude threshold (Mv) of less than 6.0 are selected for making this catalog.<br />
  
#### 2. Testing - Testing as well as implementation code of the proposed star identification algorithm
&nbsp;&nbsp;&nbsp;&nbsp;Proposed_technique.m -- Code for testing and implementation of the proposed technique in an ideal case scenario (i.e. without any positional deviation, false stars or magnitude uncertainty).<br />
&nbsp;&nbsp;&nbsp;&nbsp;Testing_false_stars.m -- Code for testing and implementation of the proposed technique when false stars are added to the simulated star images. The number of false stars to be added can be specified in this script.<br />
&nbsp;&nbsp;&nbsp;&nbsp;Testing_magnitude_uncertainty.m -- Code for testing and implementation of the proposed technique in the scenario of magnitude uncertainty in the star images. The value of the magnitude uncertainty can be specified in the script and corresponding low magnitude stars will be deleted in the simulated star image.<br />
&nbsp;&nbsp;&nbsp;&nbsp;Testing_positional_deviation.m -- Code for testing and implementation of the proposed technique in the when the star position is deviated from its original position. The range for the positional deviation to be introduced for each star can be specified in the script and positional deviation will be introduced by selecting a random value between the range for a star.<br />
###### NOTE: The testing and implementation scripts utilize the simulation scripts as well as the input from the SPD directories. So, please change the path of this input accordingly.

#### 3. SPD - Generating the SPD for the propsoed technique
&nbsp;&nbsp;&nbsp;&nbsp;SPD_generate.m -- For generating the SPD for the propsoed technique. Specific parameters (such as the FOV, pixel size, Mv, bin_size, etc.) can be changed inside the script.<br />
&nbsp;&nbsp;&nbsp;&nbsp;SPD_angles_Mv_6.txt -- SPD of the relative angles generated from the above script with a magnitude threshold (Mv) of 6.0. This SPD should be given as an input to the Testing scripts.<br />\
&nbsp;&nbsp;&nbsp;&nbsp;SPD_dist.txt -- SPD of the radial distances generated from the above script with a magnitude threshold (Mv) of 6.0. This SPD should be given as an input to the Testing scripts.<br />
