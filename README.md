## Direct numerical simulation of zero-pressure-gradient turbulent boundary layer with passive scalars up to $`Pr = 6`$ ##

This repository contains the statistical database extracted from the direct numerical simulation of zero-pressure gradient turbulent boundary layer ranging up to $`Re_\theta = 1070`$ with four different passive scalars corresponding to $`Pr=1,2,4,6`$.

For a detailed comparison of the obtained statistics against the documented data available in the literature, please take a look at our article ![](https://img.shields.io/badge/arXiv-4b4b4b?style=flat&logo=arxiv&link=https://arxiv.org/pdf/2301.12915.pdf)


You are free to use the database. For the use of DNS database in scientific communications, we request you to cite our article as:

```
@article{balasubramanian2023direct,
  title={Direct numerical simulation of a zero-pressure-gradient thermal turbulent boundary layer up to $Pr= 6$},
  author={Balasubramanian, A.G. and Guastoni, L. and Schlatter, P. and Vinuesa, R.},
  journal={arXiv preprint arXiv:2301.12915 (To appear: J. Fluid Mech.)},
  year={2023}
} 
```

### Statistics dictionary ###
                
1. How to load the statistics file?

        x = np.load('TBL_statistics.npz')

    General key naming convention:

        quantity : flow / scalar
        flow_type : fixed here (redundant) - tbl
        Momentum Re : 420 / 628 / 830 / 1070
        Data : mean / rms / skewness / flatness / mean_params / xx_budget
        Variable : u / v / w / p / s1 / s2 / s3 / s4 / us1 / ...
        Scaling : outer / inner

    Only data at 4 streamwise locations are provided. For other locations, a request shall be made to the correspondance email provided in the article.\
    For mean_params : 

        cf_wrt_x / cf_wrt_Rex / Redisp_wrt_x / Retheta_wrt_x / Retau_wrt_x / h12_wrt_x / h12_wrt_Retheta
    is possible.

    To load any variable, the format is:
    
        var = x['{quantity}_{flow_type}_{momentum_Re}_{data}_{variable}_{scaling}']

    So, to load u-RMS plot in inner-scale at $Re_\theta = 628$,

        urms = x['flow_tbl_628_rms_u_inner']
        

2. How to plot the required data?\
First, load the required data as above.\
Then, plot it as:

        plt.plot(urms[0],urms[1])

3. For list of keys available,

        for i in x.keys():
            print(i)

## Data request

If you need some additional data that might be of interest to you, please don't hesitate to contact us at:\
``Arivazhagan G B`` ![](https://img.shields.io/badge/Mail-blue?style=flat&logo=microsoftoutlook&link=mailto:argb@mech.kth.se) ![](https://img.shields.io/badge/Scholar-4b4b4b?style=flat&logo=googlescholar&link=https://scholar.google.com/citations?user=xyheRZ8AAAAJ&hl=en) ![](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin&link=https://www.linkedin.com/in/arivazhagan-geetha-balasubramanian-648b8567/)\
``Luca Guastoni`` ![](https://img.shields.io/badge/Mail-blue?style=flat&logo=microsoftoutlook&link=mailto:guastoni@mech.kth.se) ![](https://img.shields.io/badge/Scholar-4b4b4b?style=flat&logo=googlescholar&link=https://scholar.google.com/citations?user=CjwzqlcAAAAJ&hl=en) ![](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin&link=https://www.linkedin.com/in/lucaguastoni/)\
``Ricardo Vinuesa`` ![](https://img.shields.io/badge/Mail-blue?style=flat&logo=microsoftoutlook&link=mailto:rvinuesa@mech.kth.se) ![](https://img.shields.io/badge/Scholar-4b4b4b?style=flat&logo=googlescholar&link=https://scholar.google.com/citations?user=xxF-4YgAAAAJ&hl=en) ![](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin&link=https://www.linkedin.com/in/ricardo-vinuesa-91823918/)

## Upcoming

Please take a look at our work on **[Non-intrusive sensing in turbulent boundary layers via deep fully-convolutional neural networks](https://arxiv.org/pdf/2208.06024)** which has used the data sampled from the above-discussed DNS simulation.
