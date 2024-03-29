# Mini-Mental-State-Examination-Score-(MMSE)-Prediction
Development of an Artificial Neural Network (ANN) model for the prediction of MMSE score from mid line scalp EEG
Objective: To examine the possibility of predicting MMSE scores from midline EEG
Methods: an artificial neural network was developed and trained on a dataset containing spectral features (alpha, beta, theta, delta and gamma-band power, peak power, and frequency) and eventrelated potential features (LPC, N200, P300, N400 Amplitudes). These features were extracted from EEG collected from midline electrodes (Fz, Cz, and Pz).
Results: The model with all EEG features utilized for training (i.e., model did not undergo feature selection), performed better than the model with 75% of the features from the dataset (i.e., model underwent feature selection).
Conclusion: EEG features from midline electrodes can be combined with an artificial neural network to predict the MMSE score to eliminate the downsides experienced during the traditional methods of deriving an MMSE score

# Methodology
## Dataset Collection
Fifty-two (N=52) NH residents consented to enroll in an EEG cognitive evaluation study. The 1-
year study involved three evaluation time points (baseline, 6-months, and 1-year). At time point
1 (baseline), BVS and related data were obtained from 30 residents with dementia (dementia
group) and 19 residents without dementia (non-dementia group). All NH residents were fluent in
English. The MMSE: mini-mental status exam was collected from each participant.
EEG data were recorded from three midline scalp electrodes (Fz, Cz, and Pz; Ag/AgCl
electrodes) using a portable 8-channel g.Nautilus system (Gtec Medical Engineering: bandpass:
dc-250Hz, 500Hz sampling, 3-axis head motion accelerometers) and a portable computer.
Ground (forehead) and reference (earlobe) along with electro-oculogram (EOG: left the supraorbital ridge and outer canthus) were recorded using disposable electrodes. Skin-electrode
impedances were maintained below 30k impedance at each active electrode site. Following
signal amplification, conditioning, and digitization, data were transmitted via Bluetooth to the
computer using a custom USB-TTL converter subsystem to mark stimulus events.
Participants were instructed to sit motionlessly and pay attention to the auditory stimuli while
maintaining visual fixation on a cross located 2.0m away. The 5-min ERP stimulus sequence
comprised auditory stimuli combining interlaced tones and spoken word pairs.
The dependent variables are the alpha, beta, theta, and delta band powers extracted via spectral
analysis from the measured EEG while the independent variables will be MMSE

## Data Pre-Processing Techniques
1. Artifact Correction
Python was used for offline data processing. A fourth-order Butterworth filter (0.3-20Hz)
and a Notch filter (60Hz) were applied to the raw EEG data. EOG artifacts were
corrected with adaptive filtering.
2. ERPs Generation6
Established methods, namely, segmentation (−100–900ms), baseline correction (-100-
0ms), and conditional averaging (tones: standard vs deviant; and word-pairs: congruent
vs incongruent) were used to derive the ERP responses.
3. Band Power, Peak Power & Frequency Generation
The EEG power spectrum was obtained by a Fast Fourier Transformation of the EEG
signal using a rectangular window. From the generated power spectrum, the band power,
peak power, and peak frequency were calculated in the following frequency bands: delta
(0–3.99 Hz), theta (4–7.99 Hz), alpha (8–12.99 Hz), and beta (13–30 Hz).

## Results
Hyperparameters of both models after optimization

<img width="587" alt="Screen Shot 2022-04-26 at 11 50 38 AM" src="https://user-images.githubusercontent.com/70718280/165371513-2fa10afe-8f00-43ae-bdfd-73bfe8e010a2.png">

## References
[1] M. Scazufca, O. P. Almeida, H. P. Vallada, W. A. Tasse, and P. R. Menezes,
“Limitations of the Mini-Mental State Examination for screening dementia in a
community with low socioeconomic status,” European Archives of Psychiatry and
Clinical Neuroscience, vol. 259, no. 1, pp. 8–15, Jun. 2008, doi: 10.1007/s00406-008-
0827-6.

[2] S. Ruiz-Gómez et al., “Automated Multiclass Classification of Spontaneous EEG
Activity in Alzheimer’s Disease and Mild Cognitive Impairment,” Entropy, vol. 20, no.
1, p. 35, Jan. 2018, doi: 10.3390/e20010035.

