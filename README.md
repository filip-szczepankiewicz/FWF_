﻿## Free Waveform Encoding sequence resources

This repository contains manuals and standard configurations for the FWF sequence developed at Lund University and Harvard Medical School by Filip Szczepankiewicz, Carl-Fredrik Westin and Markus Nilsson.

## Related resources

Below is a collection of related resources that may help in the implementation, design and analysis of experiments related to the FWF sequence.


## Multidimensional analysis framework (MD-dMRI)

[Multidimensional diffusion MRI (MD-dMRI) framework](https://github.com/markus-nilsson/md-dmri) is a family of conceptually related methods relying on advanced gradient modulation schemes and data processing approaches to simultaneously quantify several microstructural and dynamical properties of tissue by separating their effects on the detected MRI signal into multiple acquisition and analysis dimensions.

This GitHub repository mainly contains MATLAB software for analysis of MD-dMRI data, and also some auxiliary routines for setup of acquisition protocols, motion correction, and image visualization.

[Reference: M. Nilsson, F. Szczepankiewicz, B. Lampinen, A. Ahlgren, J. de Almeida Martins, S. Lasic, C-F. Westin, D. Topgaard. An open-source framework for analysis of multidimensional diffusion MRI data implemented in MATLAB. Proc. Intl. Soc. Mag. Reson. Med. 26 (2018), Paris, France.](https://www.researchgate.net/profile/Filip_Szczepankiewicz/publication/325595277_An_open-source_framework_for_analysis_of_multidimensional_diffusion_MRI_data_implemented_in_MATLAB/links/5b179cedaca272d24cc43a0e/An-open-source-framework-for-analysis-of-multidimensional-diffusion-MRI-data-implemented-in-MATLAB.pdf)
<br/><br/>

## Gradient waveform optimization for tensor-valued encoding (NOW)

[Numerical Optimization of gradient waveforms (NOW)](https://github.com/jsjol/NOW) is MATLAB package for flexible generation of waveforms that enable q-space trajectory imaging (QTI) for tensor-valued diffusion encoding.

[Reference: Sjölund, J., Szczepankiewicz, F., Nilsson, M., Topgaard, D., Westin, C. F., & Knutsson, H. (2015). Constrained optimization of gradient waveforms for generalized diffusion encoding. Journal of Magnetic Resonance, 261, 157-168.](https://www.sciencedirect.com/science/article/pii/S1090780715002451)
<br/><br/>

## Concomitant gradient analysis tools (CFA)

[The concomitant field analysis (CFA) tool](https://github.com/markus-nilsson/md-dmri/tree/master/tools/cfa) is part of the [MD-dMRI framework](https://github.com/markus-nilsson/md-dmri), and allows for the design and analysis of Maxwell terms in arbitrary gradient waveforms.

[![](https://github.com/filip-szczepankiewicz/md-dmri/blob/master/tools/cfa/cfa_example_figure.jpg)](https://github.com/markus-nilsson/md-dmri/tree/master/tools/cfa)

[Reference: Szczepankiewicz F, Westin, C‐F, Nilsson M. Maxwell‐compensated design of asymmetric gradient waveforms for tensor‐valued diffusion encoding. Magn Reson Med. 2019;00:1–14. https://doi.org/10.1002/mrm.27828](https://doi.org/10.1002/mrm.27828)
<br/><br/>

## Peripheral nerve stimulation prediction tools (SAFE model)

[The SAFE model framework](https://github.com/filip-szczepankiewicz/safe_pns_prediction) contains a MATLAB implementation of the SAFE model used predict PNS in Siemens MRI systems based on any given gradient waveform and hardware configuration.

[![](https://github.com/filip-szczepankiewicz/safe_pns_prediction/blob/master/safe_example_figure.jpg)](https://github.com/filip-szczepankiewicz/safe_pns_prediction)

[Reference: Szczepankiewicz F, Westin, C-F, Nilsson M. Maxwell-compensated design of asymmetric gradient waveforms for tensor-valued diffusion encoding. Magn Reson Med. 2019;00:1–14. https://doi.org/10.1002/mrm.27828](https://onlinelibrary.wiley.com/doi/abs/10.1002/mrm.27828)
<br/><br/>

## Free waveform sequence header extraction tools

[The free waveform header tools](https://github.com/filip-szczepankiewicz/fwf_header_tools) are used to encode and decode information that is specific to the FWF sequence. The code provides an abstraction to ENCODE blocks of typed vectors in base64. This can be used to store floating point waveforms in an efficient manner. The code also includes corresponding decoders with prototype implementation in PYTHON and MATLAB. A specific implementation exists for the FWF sequence (v1.12 or later) developed for Siemens MRI systems.

[![Schematic example of software function.](https://github.com/filip-szczepankiewicz/fwf_header_tools/blob/master/fwf_header_example_fig.jpg)](https://github.com/filip-szczepankiewicz/fwf_header_tools)

[Reference: F Szczepankiewicz, S Hoge, C-F Westin. Linear, planar and spherical tensor-valued diffusion MRI data by free waveform encoding in healthy brain, water, oil and liquid crystals. Data in Brief (2019)](nolinkyet)
<br/><br/>

## Examples of brain protocols and performance at multiple systems

[The repository](https://github.com/filip-szczepankiewicz/Szczepankiewicz_PONE_2019) contains detailed information about experimental setup, waveforms, sampling schemes and fit setting for DIVIDE or QTI at 1.5T, 3T and 7T scanners.

[Reference: Szczepankiewicz F, Sjölund J, Ståhlberg F, Lätt J, Nilsson M. Tensor-valued diffusion encoding for diffusional variance decomposition (DIVIDE): Technical feasibility in clinical MRI systems. PLoS ONE. 2019;14(3):e0214238. https://doi.org/10.1371/journal.pone.0214238](https://doi.org/10.1371/journal.pone.0214238)
<br/><br/>

## Open source tensor-valued diffusion encoded data
Under construction...
<br/><br/>


## Seminar on the benefit of using tensor-valued diffusion encoding (YouTube) 

The talk ["'Fat' B-tensors and Diffusion Tensor Distributions"](https://www.youtube.com/watch?v=o4LYijV90Tg&t=1241s) was presented at a conference at Cardiff University entitled ‘A spin thro’ the history of restricted diffusion MR’ on January 31st and February 1st 2017. The conference was hosted by the Cardiff University Brain Research Imaging Centre and was sponsored by Siemens Healthineers and the EPSRC.

[![](/figures/fat_b_seminar_figure.jpg)](https://www.youtube.com/watch?v=o4LYijV90Tg&t=1241s)

[Reference: F. Szczepankiewicz, D. van Westen, E. Englund, C-F. Westin, F. Ståhlberg, J. Lätt, P.C. Sundgren, M. Nilsson. The link between diffusion MRI and tumor heterogeneity: Mapping cell eccentricity and density by diffusional variance decomposition (DIVIDE). NeuroImage 142, p. 522-532, 2016](https://www.sciencedirect.com/science/article/pii/S1053811916303457)
<br/><br/>
