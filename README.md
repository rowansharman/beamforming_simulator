# Beamforming Array Simulator
Beamforming microphone arrays can spatially filter sound to remove background noise and isolate sound coming from a focus point. This Mathematica code is my attempt to simulate the rejection pattern of an arbitrary beamforming microphone array in three-dimensional space.

There are three files here to facilitate development and understanding, but only `beamformingSimulator.nb` runs the full 3D simulation.

##### How it Works:
- Calculate the distances between the intended focus point and each of the microphones and convert these distances to time delays
- Generate a sine wave at the test frequency at each point in space
- For each point, vary the test signal phase to maximize the sum of the amplitudes measured at each mic
  - This can be most easily visualized and understood by running `manipulateMax.nb`, which simulates an arbitrary 1D array with the source placed axially
  - For points near the focus, this amplitude will be high. For points outside of the focus, this amplitude will be low for highly selective arrays (the goal)
  - Basically, high frequencies and large arrays work better than low frequencies and small arrays
- The frequency response of an arbitrary 1D array with the source placed axially can be visualized with `freqResponse.nb`

Because the simulation relies heavily on `Maximize`, it runs very slowly. Be warned.

I'm by no means an expert on either beamforming or Mathematica, so if I've made any grave errors in either respect, please let me know. I currently have no way to validate the simulation.

###### Example 3D gain pattern output:
![3D gain pattern for an array](3dModel_small.jpg)
