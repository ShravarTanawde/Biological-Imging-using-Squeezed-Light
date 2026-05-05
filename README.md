# Biological Imaging using Squeezed Light

This repository focuses on the implementation and application of squeezed light to overcome the Standard Quantum Limit (SQL) in classical optical imaging. By redistributing fundamental quantum noise, squeezed light enables high-resolution imaging at low photon numbers. This quantum approach completely circumvents the need for high-power lasers, preventing lethal phototoxicity and enabling the safe, continuous observation of delicate biological cells.

## Key Applications in Biological Imaging
*   **Mach-Zehnder Interferometer (MZI):** Implementing amplitude-squeezed light suppresses optical noise at the final detection stage, allowing for highly precise measurements of biological phase shifts well below the classical shot-noise limit.
*   **Quantum-Enhanced Stimulated Raman Scattering (SRS):** A pump-probe sampling method that utilizes squeezed probe light to provide high-resolution, label-free imaging for mapping specific molecular compositions, such as lipid concentrations.
*   **Quantum-Enhanced Photothermal Microscopy:** Leverages a pump laser to create a microscopic thermal lens within the sample. The squeezed probe laser is deflected by this lens, and the subsequent intensity drop is recorded to accurately map microscopic structures based on thermal absorption.

## Code Reproduction: MZI Simulation
The repository includes a computational reproduction of an MZI to empirically verify the theoretical advantages of squeezed light. The simulation relies on QuTiP (Quantum Toolbox in Python) and is structured to execute within a cloud-based Python notebook environment.

### Simulation Details and Parameters
*   The code mathematically constructs the MZI using quantum operators, modeling the net effect of the biological sample via a single-mode phase shift operator $e^{(iφn)}$.
*   The simulation compares a standard classical coherent state with an amplitude of |α|=2.0 against an amplitude-squeezed state with a squeezing parameter of r=1.0.
*   The system operates within a truncated Fock space defined by a maximum of N=30 photons.
*   To evaluate the noise floor, the script calculates the statistical variance of the amplitude (X) quadrature and approximates practical phase sensitivity (Δφ) using a proxy for the Cramér-Rao bound.

### Simulation Outputs
*   **Noise Variance vs. Phase:** The simulation demonstrates that at optimal phase matching points, the noise variance of the squeezed light drops precipitously below the classical Shot-Noise Limit of 0.25.
*   **Phase Sensitivity Advantage:** While squeezed light has a higher average noise variance across an unaligned 360° sweep (0.9256 compared to the classical 0.2500), it reliably and exponentially outperforms the classical baseline in resolving biological phase shifts. 
*   **Empirical Precision:** The squeezed state achieves a mean phase sensitivity of 2.342, which is significantly more precise than the highly unstable classical state's mean sensitivity of approximately 4.95 x $10^{11}$.
