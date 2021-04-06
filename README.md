## Free Waveform (FWF) encoding pulse sequence resources

### Overview
This repository contains materials and tools to support the implementation and use of the "Free Waveform" (FWF) MRI pulse sequence. The sequence was developed for the Philips and Siemens platforms by Filip Szczepankiewicz, Carl-Fredrik Westin and Markus Nilsson at Lund University and Harvard University. Similar pulse sequences have also been implemented on GE, United Imaging and Bruker platforms (see info below).

The sequence is a diffusion-weighted spin-echo that facilitates the execution of user-defined gradient waveforms for the purposes of tensor-valued diffusion encoding and other methods that require arbitrary modulation of the gradients.
<br/><br/>

### Getting the sequence
**Siemens**  
Please send an email to the [diffusion MRI group at Lund University](mailto:markus.nilsson@med.lu.se).  
Check the [**list of compiled variants**](/Siemens/readme.md) to see if the sequence is available for your system. In special cases we may compile the sequence for other versions.  

**Philips**  
Please contact Maarten Versluis (maarten.versluis@philips.com).

**GE**  
Please contact Timo Schirmer (timo.schirmer@med.ge.com).

**United Imaging**  
Please contact Weiguo Zhang (weiguo.zhang@united-imaging.com).

**Bruker**  
An implementation for TopSpin, by Daniel Topgaard at Lund University, is available [here](https://github.com/filip-szczepankiewicz/md-dmri/tree/master/acq/bruker).  
An implementation for ParaVision, by Mathew Budde at Medical College of Wisconsin, is available [here](https://osf.io/4nkg3/).
<br/><br/>

### Installing the sequence
**Siemens**  
General instructions for sequence installation and a manual for the "simple" sequence setup is found [here](/Siemens/Documents/).  

**Philips, GE and United Imaging**  
Instructions for installation and setup are provided by the vendor.
<br/><br/>

### Designing the experiment \[[Review paper](https://www.sciencedirect.com/science/article/pii/S0165027020304301)\]
The design of the gradient waveforms (b-tensor shapes) and the signal sampling schemes (b-values, rotations etc.) must be considered when setting up he experiment. A comprehensive review of the factors that need be considered is found [here](https://www.sciencedirect.com/science/article/pii/S0165027020304301). In general, the design is informed by the hardware, the intended analysis technique and the organ/subject characteristics. Below, we have collected tools and examples related to the experimental design.  

**Waveform design**  
A framework for numerical gradient waveform optimization was published by [Sjölund et al.](https://doi.org/10.1016/j.jmr.2015.10.012) and is available on [GitHub](https://github.com/jsjol/NOW). This framework also includes [concomitant gradient compensation](https://doi.org/10.1002/mrm.27828), as well as [motion encoding compensation](https://onlinelibrary.wiley.com/doi/10.1002/mrm.28551).

**Example sampling schemes**  
Examples of sampling schemes appropriate for a given combination of organ and analysis technique are found in the [SamplingSchemes](/SamplingSchemes) folder.  

**Published waveforms and sampling schemes**  
The following is a list of published sampling schemes:  

* B-tensor encoding in brain in multiple MRI systems \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_PONE_2019)\] \[[Citation](https://doi.org/10.1371/journal.pone.0214238)\]
* Open source data encoded with LTE, PTE and STE  \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_DIB_2019)\] \[[Citation](https://doi.org/10.1016/j.dib.2019.104208)\]
* Diffusion-T2-relaxation correlation for compartment imaging \[[GitHub](https://github.com/belampinen/lampinen_mrm_2019)\] \[[Citation](https://doi.org/10.1002/mrm.28216)\]
* Motion-compensated gradient waveforms by numerical optimization \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_MRM_2020)\] \[[Citation](https://onlinelibrary.wiley.com/doi/10.1002/mrm.28551)\]
<br/><br/>

### Image postprocessing

Postprocessing can be done using regular tools developed by the diffusion 
MRI community. Special care is however needed for correction of distortions 
due to eddy currents and subject movement to avoid artefacts (see 
[Nilsson et al., 2015](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0141825)).
This can be done with various tools

* Multidimensional analysis framework (see [below](#multidimensional-analysis-framework-github-citation))
* The [eddy tool](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy) from FSL (however, see [this note](/Misc/Postprocessing_Eddy.MD)).
<br/><br/>

### Model fitting and interpretation
We have published an [extensive framework in open source](https://github.com/markus-nilsson/md-dmri) for the analysis of data encoded by b-tensors and more. Please refer to these [instructions](https://github.com/markus-nilsson/md-dmri#how-to-start) for the setup of analysis pipelines, and the interpretation of [model parameters](https://github.com/markus-nilsson/md-dmri/tree/master/methods#md-dmri-methods).

**Example of analysis pipeline**  
* A brief example of how to calculate QTI parameters from data (based on the [DIB2019](https://github.com/filip-szczepankiewicz/Szczepankiewicz_DIB_2019) data set) can be found [here](https://github.com/filip-szczepankiewicz/Szczepankiewicz_DIB_2019/blob/master/EXAMPLE/dtd_covariance/dib_dtd_covariance_example1.m).
* A thorough, step-by-step, example including motion correction, QTI parameter fitting, and co-registration with anatomical sequences can be found [here](https://github.com/markus-nilsson/md-dmri/tree/master/examples/pipeline)
<br/><br/>


## External resources and references

#### General principles for gradient waveform design \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_JNeuMeth_2021)\] \[[Citation](https://www.sciencedirect.com/science/article/pii/S0165027020304301)\]  
Tensor-valued diffusion encoding often requires complex gradient wavefomrs. In the design of these, features such as physiology, hardware, and diffusion physics must be considered. This paper reviews the major factors that go into the waveform design, and the tradeoffs that are considered.  
[_F. Szczepankiewicz, C-F. Westin, M. Nilsson. Gradient waveform design for tensor-valued encoding in diffusion MRI._ Journal of Neuroscience Methods 348, 2020.](https://www.sciencedirect.com/science/article/pii/S0165027020304301)
<br/><br/>
  
#### Numerical gradient waveform optimization \[[GitHub](https://github.com/jsjol/NOW)\] \[[Citation](https://doi.org/10.1016/j.jmr.2015.10.012)\]  
Numerical Optimization of gradient waveforms (NOW) is an open source MATLAB framework for flexible generation of waveforms that enable q-space trajectory imaging (QTI) for tensor-valued diffusion encoding.  
[_Sjölund, J., Szczepankiewicz, F., Nilsson, M., Topgaard, D., Westin, C. F., & Knutsson, H. (2015). Constrained optimization of gradient waveforms for generalized diffusion encoding. Journal of Magnetic Resonance, 261, 157-168._](https://doi.org/10.1016/j.jmr.2015.10.012)
<br/><br/>

#### Maxwell-compensated gradient waveforms and tools for concomitant gradient analysis \[[GitHub](https://github.com/markus-nilsson/md-dmri/tree/master/tools/cfa)\] \[[Citation](https://doi.org/10.1002/mrm.27828)\] \[[YouTube](https://www.youtube.com/watch?v=nqqzds7WS2U&feature=emb_logo)\]  
Concomitant gradient effects can introduce gross bias in dMRI measurements. By limiting the Maxwell index in numerical optimization we can remove these errors. The concomitant field analysis (CFA) tool  facilitates analysis of Maxwell terms in arbitrary gradient waveforms.  
[_Szczepankiewicz F, Westin, C‐F, Nilsson M. Maxwell‐compensated design of asymmetric gradient waveforms for tensor‐valued diffusion encoding. Magn Reson Med. 2019;00:1–14. https://doi.org/10.1002/mrm.27828_](https://doi.org/10.1002/mrm.27828)
<br/><br/>

#### Motion-compensated gradient waveforms \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_MRM_2020)\] \[[Citation](https://onlinelibrary.wiley.com/doi/10.1002/mrm.28551)\] 
Bulk motion and incoherent ballistic motion can be misinterpreted as diffusion. This framework extends numerical optimization of waveforms to include nulling of motion encoding to arbitrary order.  
[_F Szczepankiewicz, J Sjölund, E Dall’Armellina, S Plein, J E Schneider, I Teh, and C-F Westin. Motion-compensated gradient waveforms for tensor-valued diffusion encoding by constrained numerical optimization._ Magn Reson MEd, 2020](https://onlinelibrary.wiley.com/doi/10.1002/mrm.28551)
<br/><br/>

#### Multidimensional analysis framework \[[GitHub](https://github.com/markus-nilsson/md-dmri)\] \[[Citation](https://www.researchgate.net/profile/Filip_Szczepankiewicz/publication/325595277_An_open-source_framework_for_analysis_of_multidimensional_diffusion_MRI_data_implemented_in_MATLAB/links/5b179cedaca272d24cc43a0e/An-open-source-framework-for-analysis-of-multidimensional-diffusion-MRI-data-implemented-in-MATLAB.pdf)\]  
Multidimensional diffusion MRI (MD-dMRI) framework is an open source MATLAB repository that facilitates analysis of data acquired with tensor-valued diffusion encoding and its correlation with relaxation weighting.  
[_M. Nilsson, F. Szczepankiewicz, B. Lampinen, A. Ahlgren, J. de Almeida Martins, S. Lasic, C-F. Westin, D. Topgaard. An open-source framework for analysis of multidimensional diffusion MRI data implemented in MATLAB. Proc. Intl. Soc. Mag. Reson. Med. 26 (2018), Paris, France._](https://www.researchgate.net/profile/Filip_Szczepankiewicz/publication/325595277_An_open-source_framework_for_analysis_of_multidimensional_diffusion_MRI_data_implemented_in_MATLAB/links/5b179cedaca272d24cc43a0e/An-open-source-framework-for-analysis-of-multidimensional-diffusion-MRI-data-implemented-in-MATLAB.pdf)
<br/><br/>

#### Peripheral nerve stimulation prediction \[[GitHub](https://github.com/filip-szczepankiewicz/safe_pns_prediction)\] \[[Citation](https://doi.org/10.1002/mrm.27828)\]  
This open source framework contains a MATLAB implementation of the [SAFE model by Hebrank and Gebhardt](https://cds.ismrm.org/ismrm-2000/PDF7/2007.PDF) which can be used predict PNS in Siemens MRI systems based on any given gradient waveform and hardware configuration.  
[_Szczepankiewicz F, Westin, C-F, Nilsson M. Maxwell-compensated design of asymmetric gradient waveforms for tensor-valued diffusion encoding. Magn Reson Med. 2019;00:1–14. https://doi.org/10.1002/mrm.27828_](https://doi.org/10.1002/mrm.27828)
<br/><br/>

#### Free waveform (FWF) sequence header extraction \[[GitHub](https://github.com/filip-szczepankiewicz/fwf_header_tools)\] \[[Citation](https://doi.org/10.1016/j.dib.2019.104208)\] 
The free waveform header tools are used to encode and decode information that is specific to the FWF sequence. The code provides an abstraction to ENCODE blocks of typed vectors in base64. This can be used to store floating point waveforms (and any other data type) in an efficient manner. The code also includes corresponding decoders with prototype implementation in PYTHON and MATLAB. A specific implementation exists for the FWF sequence (v1.12 and later) developed by FSz for Siemens MRI systems.  
[_F Szczepankiewicz, S Hoge, C-F Westin. Linear, planar and spherical tensor-valued diffusion MRI data by free waveform encoding in healthy brain, water, oil and liquid crystals. Data in Brief (2019), DOI: https://doi.org/10.1016/j.dib.2019.104208_](https://doi.org/10.1016/j.dib.2019.104208)
<br/><br/>

#### Example protocols at multiple systems \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_PONE_2019)\] \[[Citation](https://doi.org/10.1371/journal.pone.0214238)\]  
The repository contains detailed information about experimental setup, waveforms, sampling schemes and fit setting for DIVIDE or QTI at 1.5T, 3T and 7T scanners as part of the publication by Szczepankiewicz et al. 2019 in PoNE.  
[_Szczepankiewicz F, Sjölund J, Ståhlberg F, Lätt J, Nilsson M. Tensor-valued diffusion encoding for diffusional variance decomposition (DIVIDE): Technical feasibility in clinical MRI systems. PLoS ONE. 2019;14(3):e0214238. https://doi.org/10.1371/journal.pone.0214238_](https://doi.org/10.1371/journal.pone.0214238)
<br/><br/>

#### Open source tensor-valued dMRI data \[[GitHub](https://github.com/filip-szczepankiewicz/Szczepankiewicz_DIB_2019)\] \[[Citation](https://doi.org/10.1016/j.dib.2019.104208)\]  
This is an open source repository that supplies diffusion-MRI data with tensor-valued diffusion encoding. Data is available in a healthy human brain in vivo as well as water, oil and liquid crystal phantoms. The repository also contains detailed information and resources concerning the experiment and its design.  
[_F. Szczepankiewicz, S. Hoge, C-F. Westin. Linear, planar and spherical tensor-valued diffusion MRI data by free waveform encoding in healthy brain, water, oil and liquid crystals. Data in Brief (2019), DOI: https://doi.org/10.1016/j.dib.2019.104208_](https://doi.org/10.1016/j.dib.2019.104208)
<br/><br/>

#### Seminar on tensor-valued diffusion encoding \[[YouTube](https://www.youtube.com/watch?v=o4LYijV90Tg&t=1241s)\] \[[Citation](https://doi.org/10.1016/j.neuroimage.2016.07.038)\]  
The talk "'Fat' B-tensors and Diffusion Tensor Distributions" was presented at a conference at Cardiff University entitled "A spin thro’ the history of restricted diffusion MR" on January 31st and February 1st 2017. The conference was hosted by the Cardiff University Brain Research Imaging Centre and was sponsored by Siemens Healthineers and the EPSRC.  
[_F. Szczepankiewicz, D. van Westen, E. Englund, C-F. Westin, F. Ståhlberg, J. Lätt, P.C. Sundgren, M. Nilsson. The link between diffusion MRI and tumor heterogeneity: Mapping cell eccentricity and density by diffusional variance decomposition (DIVIDE). NeuroImage 142, p. 522-532, 2016. DOI: https://doi.org/10.1016/j.neuroimage.2016.07.038_](https://doi.org/10.1016/j.neuroimage.2016.07.038)
