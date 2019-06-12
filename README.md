# OpenVibe-to-Python
Code for sending out signals from Open-vibe Designer to Python for Data Analysis/Visualization using Pylsl 

## Requirements
* Python 3

* pylsl 1.13.1

* scipy

* numpy

* matplotlib


### Install dependencies using pip
Pylsl is a Python interface to the Lab Streaming Layer (LSL). LSL is an overlay network for real-time exchange of time series between applications, most often used in research environments. LSL has clients for many other languages and platforms that are compatible with each other.

Ensuring Python3 is installed: install pylsl,scipy,numpy,matplotlib
```
 pip install pylsl 
```
Other dependencies can also be installed in similar fashion.
```
 pip install scipy
```
```
 pip install numpy 
```
```
 pip install matplotlib
```

## Usage Guide
The functions defined directly give you the average power of a signal in a specific frequency range, using both Welch and the multitaper spectral estimation methods. The raw data from EEG Device(We used ANT-Neuro EEGO mylab) is sent to python script using Lab Streaming Layer via Open-Vibe Designer.In Designer, the data can be acquired from Device and then a pipe can be made between signal acquiring block and Lab Streaming Layer block. This is a simple connection between two blocks which can be found here (Acquisition Server -> LSL) http://openvibe.inria.fr/how-to-use-labstreaminglayer-in-openvibe/.

You need to specify the number of Channels and Sampling Frequency and feed it to _main() function. By default, _main() gives Relative power but you can make changes for it to give Absolute Power. You can get more info on Power Density : https://raphaelvallat.com/bandpower.html

Currently 3 Bands are being focused on Theta(4hz,7hz),Alpha(8hz,13hz) and Gamma(13hz,30hz).
