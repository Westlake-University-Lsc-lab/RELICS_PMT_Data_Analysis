# Polariser ratio test

## Guide

### Always, check hardware connection first
### Make sure everything is in position, check the voltage.

go to path ```cd /etc/DAW_Demo/```

to search for everything in path, use ```ls -lrth /etc/DAW_Demo/```

### Start collecting data

change file name with ```vi DAW_Config.txt``` check trigger(adc), date, PMT id number, LED voltage, pulse width, etc.

press ```i``` to insert anything

press ```Esc``` to end insertion

```:wq``` to save and quit

```Ctrl+z``` to quit anyway

```DAW_Demo```	to launch the digitizer

press ```s``` to start / stop counting

press ```q``` to quit

### Analyse data

To quickly analysis the results, use 

```python3 /home/yjj/pmt8520/check_trigger_rate.py file_name```

### Note

All commands must be under the correct account: ```daq@daq-RH411```

To sign in, try ```su daq``` in terminal.

Password: ```Password```

```History``` 	for command history.