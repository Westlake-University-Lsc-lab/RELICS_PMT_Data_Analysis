# RELICS PMT test data analysis

## Guide
To install the package, run the following command in terminal:
``` git clone git@github.com:Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis.git ```

``` cd PolariserCheck ```

``` git checkout (branch_name) ```

To process data files from mulit runs(LED runs for example), run the following command in terminal:
``` ls -lrth   --time-style=+%Y-%m-%d\ %H:%M  /mnt/data/PMT/R8520_406/LV2415_anodereadout_LV2414_dualreadout_20240821_LED_1.7V_15ns_400_ratio_run* >> runlist/LED_1.7V_11ns_400_ratio_runs ```

you need to edit the `` runlist/LED_1.7V_11ns_400_ratio_runs `` file with:
``` vim runlist/LED_1.7V_11ns_400_ratio_runs ```

``` ctl+v ```

``` --> right arrow till 'MB', and leave the 'year-month-day-hour-minute '  ```

``` :wq! ```

the ``runlist/LED_1.7V_11ns_400_ratio_runs``shows like this:
``` more runlist/LED_1.7V_11ns_400_ratio_runs ```

`` 2024-08-21 14:49 /mnt/data/PMT/R8520_406/LV2415_anodereadout_LV2414_dualreadout_20240821_LED_1.7V_11ns_400_ratio_run0_raw_b0_seg0.bin ``
`` 2024-08-21 15:03 /mnt/data/PMT/R8520_406/LV2415_anodereadout_LV2414_dualreadout_20240821_LED_1.7V_11ns_400_ratio_run1_raw_b0_seg0.bin ``

The processed diagrams are saved in ```/home/lrz/pmt_saturation/folder_name/img/```

## Experiment
The setup of the experiment is shown in the 
![box diagram](https://github.com/Chocolirz/RELICS_PMT_Data_Analysis/blob/main/img/experiment_setup.pdf).

## Calibrations
### Dark rate
Dark rate is tested every time HV is applied. A reasonable range is several hundreds of Hertz. 

### Polariser transmission ratio
Data is stored in the laboratory's server, analysised by ![this notebook](https://github.com/Chocolirz/RELICS_PMT_Data_Analysis/blob/main/PolariserCheck/check_readout.ipynb).

### Linearity
To find out the minimum energy for saturation, we tested the linearity of our PMT by comparing the pulse area of two PMTs. 

Data was analysised by 
## Tests
### Time constant of recharge
### Dynode readout