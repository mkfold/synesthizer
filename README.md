# Synesthizer
/ˌsinəsˈTHīzər/ --- generating sound from video.

**tl;dr**: the code you're looking for is in `videosynth.py`.

This project was developed for the 2019 WWU ACM Hackathon. Within 24 hours, we went through a few iterations and a number of ideas until eventually converging on using video features to parameterize a synthesizer and sequencer. In the end, our submission took first place in the competition!

The name *Synesthizer* is a portmanteau of "synesthesia" and "synthesizer", a nod to the parallel between image-to-sound generation and synesthesia, where stimulation of one sense can elicit sensations with a different sense.

At final submission, our synthesizer used image brightness, sharpness, and movement intensity to control such parameters as LPF filter cutoff and resonance, per-oscillator amplitude, rate of change of melody, and fine-tuning of the lead oscillator. Time-permitting and with more compute resources (this was all done on a Chromebook!), we would have experimented with richer features, but we still achieved satisfactory results with the simple features we ended up using.

To make some music, invoke the script as follows: `python videosynth.py -m video_file.mp4`

If you have a webcam, simply run `python videosynth.py` without a video file path to use video capture.

## Requirements
The main script requires the following:
* numpy
* pyo
* pyo-tools
* opencv2 (and opencv-python)
* mingus

Other python scripts in this repo may also require librosa and pysoundfile.

The early Processing version of this script requires Processing, processing-video, processing-sound, processing-imageprocessing, and beads.

## Other files
`utils.py` contains a host of helper functions for note and chord generation.

`videosynth.pde` is our original Processing implementation, which got ditched because envelope gen with Pyo was easier and we managed to get Pyo to work on one of our own machines.

The `experiments` directory contains a few scripts made early in the development of this project to generate raw PCM signals directly from images and video.

## Authors
Mia (@xxmia)  
Christian Careaga (@CCareaga)  
Ryan Haight (@ryanhaight444)  
Daniel Tarnu
