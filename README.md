# Automatic Music Transcription EClub

This repository contains the research done and the codes written for the semester project - Automatic Music Transcription, offered by Electronics Club IIT Kanpur.

We referred to various research papers:
[Automatic Music Transcription with Convolutional Neural Network using intuitive filter shapes](https://github.com/shrutinisal/AMT_EClub/blob/master/AMT.pdf)

## Preprocessing
Worked on the MAPS Dataset of size around 15 GB. To extract information about frequency, time and amplitude from a given audio files,converted them to spectrograms by employing the use of:

 1.Constant Q Transform - For a span of 7 octaves with 36 frequency bins each, the total number of frequency bins taken was 252. We chose a sample rate of 44100 and a 'hop length' of 512 (Powers of 2 are generally used). Used Librosa Library for computing CQT and stored it in the form of numpy array.
 
 2.Short-Time Fourier Transform - For maximum frequency resolution with STFT, window size should be taken as the entire span of the file. However, this is accompanied by very low time resolution (uncertainty principle for the Fourier Transform).

 We chose CQT over STFT because CQT has logarithmically spaced bins.This is advantageous as the harmonic pattern stays
constant for each note, or is pitch invariant, which makes training the neural network
much easier.

Note:Extract the MAPS dataset completely before preprocessing.
