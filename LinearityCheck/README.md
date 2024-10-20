# Linearity Check

This is a Python script to check the linearity of the PMT signal. 

## Background

[PandaX's recent paper](https://arxiv.org/abs/2401.00373) stated that their initial PMT base design leads to significant saturation of the individual PMTs when the signal exceeds $1000\ {\rm PEs}$. In [PolariserCheck](https://github.com/Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis/tree/main/PolariserCheck), we have already provided a transmission ratio of the crossed polars, which can provide reference for the saturated PMT when our signal exceeds $1000\ {\rm PEs}$. 

## Operations and condition

The linearity check will be performed with identical setups and conditions, therefore there's no need to repeat [the instructions before](https://github.com/Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis/blob/main/PolariserCheck/README.md). 

We used several $3\ {\rm dB}$ attenuators (voltage dividers) to reduce the amplitude and avoid ADC saturation. Theoretically, this allows us to measure signals up to $64\ {\rm V}$ with the same percentage error. The next step is therefore to simulate high-energy signals and check the linearity to see when PMT starts to saturate. Theoretically, the transformation between dB and ratio is:

${\rm dB} = 20\log_{10}\left(\frac{V_2}{V_1}\right).$

In RELICS experiment, the pulse width of a typicall top-entry muon signal should be in the range of $50\sim 100\ {\rm ns}$. For the $100\ {\rm ns}$ pulse width, we observed saturation around perhaps $2500\ {\rm PEs}$, which is exactly the range we expected. 

## Code structure

1. Read and process data from crossed polars and dynode readout.
2. Write data into file ```linear.txt```.
3. Normalize the data to $1$.
4. Plot the data and check the linearity.

## Results

Calibration data using crossed polars and dynode readout (collected on September 24th 2024) were both normalised to $1$ and then presented in [one single plot](https://github.com/Westlake-University-Lsc-lab/RELICS_PMT_Data_Analysis/blob/main/LinearityCheck/img/final.png). The linearity relation obtained from both ways is "almost" the same (still needs quantitative comparison). For $100\ {\rm ns}$ pulse width, the linearity was preserved until $2500\ {\rm PEs}$, and then the signal starts to saturate. Measureing the saturation time constant is the next step of our research. 

## Further

As planned, two major factors will be examined in detail:

1. The saturation time constants. 
2. Design and algorithm for the dynode readout.

There are two kinds of time constant expected: time constant of saturation and recharge. They both need smaller frequency, perhaps $200\ {\rm Hz}$ or less. For recharge time constant in particular, specially-designed external trigger and LED pulse waveforms are needed. 

Currently, the biggest challenge for dynode readout is how to determine a proper value of $R_{d6}$, this may need repeated series of experiments, and the algorithm for the dynode readout may need to be examined seriously and optimized.