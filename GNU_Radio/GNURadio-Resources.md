Getting started with gnu radio :
first install gnu radio in your system follow the listed steps for linux based system
1. sudo apt upgrade
2. sudo apt install gnuradio
3. sudo apt install gr -osmosdr
 To verify just open gnu radio in terminal by 
 gnuradio-companion

Creating first file
open grc window by above mentioned command or via application
Double click the _Options_ block and name the flowgraph by editing the _Id_ and _Title_:
The _Id_ is the filename of the Python flowgraph. Name it _sineWaveFlowgraph_. The _Title_ is a description of the flowgraph. Click _OK_ to save the changes.

after naming the id and title 
Click _File : Save_ to save the GRC Flowgraph.
save as .grc file

## Adding Blocks

Blocks are added to create the first flowgraph. GNU Radio comes with a library of signal processing blocks. The blocks can be browsed using the arrows on the right. Blocks may also be searched for using _CTRL + F_ or by selecting the magnifying glass
 
Various blocks:
In GNU Radio, the Signal Source block and Audio Sink block are two common components used in signal processing flowgraphs.

1. **Signal Source Block**:
   The Signal Source block is used to generate a signal within your GNU Radio flowgraph. This block is typically used as the starting point of your processing chain. It can generate various types of signals, such as sine waves, square waves, constant values, and more. The generated signal can be used for various purposes, such as testing, modulation, and simulation.

   Properties of the Signal Source block often include parameters like:
   - Signal type (sine, square, constant, etc.)
   - Frequency
   - Amplitude
   - Sample rate
   - Phase
   - Repeat or no-repeat mode

  
2. **Audio Sink Block**:
   The Audio Sink block is used to output audio data from your GNU Radio flowgraph to an audio output device, such as your computer's speakers or headphones. It allows you to listen to or monitor the processed audio signal.

   Properties of the Audio Sink block often include parameters like:
   - Sample rate
   - Number of audio channels (mono or stereo)
   - Device selection (if multiple audio output devices are available)
   
## Throttle, QT GUI Frequency Sink, and QT GUI Time Sink.

1. **Throttle Block**:
   The Throttle block is used to control the rate at which samples are processed in a GNU Radio flowgraph. It's often used to ensure that the flowgraph's processing speed matches the required rate for real-time processing or visualization.

   The Throttle block has a parameter called "Sample Rate" which determines how fast the samples are processed. If the incoming data rate is higher than the throttle's sample rate, the excess samples will be discarded, preventing buffer overflows. If the incoming data rate is lower, the Throttle block will duplicate or interpolate samples to meet the desired rate.

  
2. **QT GUI Frequency Sink Block**:
   The QT GUI Frequency Sink block is used to visualize the frequency-domain representation of a signal. It provides a real-time spectrogram plot, showing how the signal's frequency components change over time.

   This block allows you to monitor the spectrum of a signal and is particularly useful for visualizing modulated signals, identifying frequency components, and analyzing spectral characteristics.

   Parameters of the QT GUI Frequency Sink block often include:
   - Title of the plot window
   - Y-axis label
   - Frequency range
  

3. **QT GUI Time Sink Block**:
   The QT GUI Time Sink block is used to display the time-domain representation of a signal. It provides a real-time plot showing how the signal changes over time.

   This block is useful for visualizing the waveform of a signal, checking for signal quality, and observing changes in amplitude and phase.

   Parameters of the QT GUI Time Sink block often include:
   - Title of the plot window
   - X-axis label
   - Y-axis range


Both the QT GUI Frequency Sink and QT GUI Time Sink blocks create windows with plots that dynamically update as the flowgraph runs. These blocks are part of the `gnuradio.qtgui` module and are great for visualizing signals during development and debugging.



