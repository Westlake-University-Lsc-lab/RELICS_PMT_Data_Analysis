# Linearity Check

This is a Python script to check the linearity of the PMT signal. 

## Background

[PandaX's recent paper](https://arxiv.org/abs/2401.00373) stated that their initial PMT base design leads to significant saturation of the individual PMTs when the signal exceeds 1000 PEs. In [PolariserCheck](https://github.com/Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis/tree/main/PolariserCheck), we have already provided a transmission ratio of the crossed polars, which can provide reference for the saturated PMT when our signal exceeds 1000 PEs. 

## Operations and condition

The linearity check will be performed with identical setups and conditions, therefore there's no need to repeat [the instructions before](https://github.com/Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis/blob/main/PolariserCheck/README.md). 

## New factors

Dynode readout, which was collected in CH2, will appear here and be examined in detail for later tests. 

## Further

As planned, two major factors will be examined in detail:

1. The saturation time constants. 
2. Design and algorithm for the dynode readout.

There are two kinds of time constant expected: time constant of saturation and recharge. They both need smaller frequency, perhaps $200 Hz$ or less. For recharge time constant in particular, specially-designed external trigger and LED pulse waveforms are needed. 

Currently, the biggest challenge for dynode readout is how to determine a proper value of $R_{d6}$, this may need repeated series of experiments, and the algorithm for the dynode readout may need to be examined seriously and optimized.