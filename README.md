# PSD-in-Plastic-Scintillator-in-Geant4-using-MLP
This project investigates neutron–gamma pulse shape discrimination (PSD) in the EJ-276 plastic scintillator using Monte Carlo simulations performed with GEANT4, including full optical photon tracking.

Neutron and gamma events were simulated at multiple discrete energies in the MeV range:
1.0, 1.5, 2.0, 2.5, 3.0, 3.5, and 4.0 MeV.  
For each energy point, a total of 4000 events were generated (2000 gamma and 2000 neutron), consisting of 4000 neutron events and 2000 gamma-ray events, reflecting a realistic gamma-dominated radiation environment.

Optical photon arrival times were recorded and binned in the time domain. For each particle type, time-binned contributions from all events were summed bin-by-bin to construct ensemble-averaged (reference) pulse shapes. These distributions represent the average temporal scintillation response rather than single-event waveforms.

Classical pulse shape discrimination was performed using the charge comparison (CC) method, with fixed integration windows:
- Q_short: integrated charge over the first 80 ns (prompt region),
- Q_long: integrated charge over the first 350 ns (including delayed light).

In addition, waveform-level neutron–gamma discrimination was carried out using a multilayer perceptron (MLP). The network takes full time-binned pulses as input and is trained using an energy-held-out strategy, where training, validation, and testing are performed at different energies to assess robustness under energy shifts.

This framework enables a physics-driven study of PSD, including the roles of photon statistics, optical transport effects, and energy dependence.
