# 1D inversion of time-domain electromagnetic data with induced polarization effects for a sea-floor hydrothermal deposit
 KEGS Symposium, March 1, 2025, Toronto Canada

Seafloor hydrothermal deposits are polymetallic massive sulfide ore deposits formed by the precipitation of metal components contained in hot water ejected from the seafloor (JOGMEC, 2020). These deposits exhibit several key physical properties relevant to geophysical exploration:

1. **Depth**: Deposits are located at depths of 700-2000m below sea level.
2. **Seawater Conductivity**: Seawater in these regions has high conductivity (3-3.5 S/m).
3. **Ore Body Dimensions**: Ore bodies typically extend hundreds of meters horizontally and tens of meters vertically (Morozumi et al., 2020).
4. **Exposure**: Ore bodies are often exposed on the seafloor.

Laboratory studies have shown that resistivity and chargeability are diagnostic physical properties of these deposits, making them distinguishable from seawater (Nakayama et al., 2012). Hydrothermal water temperatures are measured to range from 200 to 400 °C. Studies indicate that higher temperatures correspond to lower resistivity in both seawater (Bannard, 1975) and rock samples (Takakura, 2016).

### Geophysical Methods
Time-domain electromagnetic (TEM) methods are highly sensitive to resistivity variations. The WISTEM (Waseda Integrated Seafloor Time-Domain Electromagnetic Exploration) system has been effectively used for such studies (Nakayama and Saito, 2016). Surveys conducted in several areas have demonstrated the utility of fixed measurements where the WISTEM system is landed on the seafloor. In these measurements, negative transients attributed to induced polarization (IP) effects have been observed in data collected over known deposits (Nakayama, Motoori, and Saito, 2019).

In 2018, a survey was conducted by JOGMEC in the Okinawa Trough, and data from the Fix-2 area (Area-2) highlighted the relevance of IP effects in the presence of sulfide-rich materials. A synthetic study by Motoori and Heagy (2024) simulated negative transients due to IP effects and showed the sensitivity of the method to IP parameters.

### WISTEM System and Data Analysis
The WISTEM system features a 3.5-meter square transmitter loop and a five-turn coincident receiver loop, with equipment such as the transmitter and receivers placed in the loop's center. To address potential influences of the pressure vessel on data, reference measurements are taken with the system suspended 100m above the seafloor to capture the system response.

### Objectives and Methodology
This study focuses on:

1. **Simulation of Pressure Vessel Effects**:
   - Using the two-dimensional cylindrical framework in SimPEG (Cockett et al., 2015; Heagy, 2017) and simpegEMIP (Kang, 2016), we simulate the influence of the pressure vessel.

2. **System Response Characterization**:
   - Deconvolution of reference data with the analytical response of seawater to derive a linear filter that captures the system's response. This filter will be applied in subsequent simulations and inversions.

3. **1D IP Inversion**:
   - Performing 1D IP inversion using empymod (Werthmüller, 2017) on Fix-2 data containing negative transients.

### References
- Japan Organization for Metals and Energy Security (JOGMEC), 2020. [World’s First Successful Excavation of Cobalt-Rich Seabed in the Deep Ocean](https://www.jogmec.go.jp/english/news/release/news_01_000033.html).
- Haruhisa Morozumi et al, 2020. Characteristics of seafloor hydrothermal deposits investigated by JOGMEC.
- Bannard, J.E., 1975. Effect of density on the electrical conductance of aqueous sodium chloride solutions. *Journal of Applied Electrochemistry*, 5, 43-53.
- Nakayama and Saito, 2016. Practical marine TDEM systems using ROV for ocean bottom hydrothermal deposits.
- Pelton, W.H. et al., 1978. Mineral discrimination and removal of inductive coupling with multifrequency IP. *Geophysics*.
- Motoori and Heagy, 2024. A synthetic study investigating induced polarization effects on time-domain electromagnetic data for seafloor hydrothermal deposits.
- Endo, Nakayama and Saito, A., 2024. Effective and practical interpretation of marine transient electromagnetic data (2): Quantitative interpretation.
- Takakura, 2018. Standardization of resistivity measurement of ore samples taken at seafloor hydrothermal deposits.
- Cockett et al, 2015. SimPEG: An open-source framework for simulation and gradient-based parameter estimation in geophysical applications.
- Heagy et al, 2017. A framework for simulation and inversion in electromagnetics.
- Kang and Oldenburg, D.W., 2016. On recovering distributed IP information from inductive source time-domain electromagnetic data.
- Werthmüller, 2017. An open-source full 3D electromagnetic modeler for 1D VTI media in Python: empymod.
- Oldenburg and Li, 2005. Inversion for applied geophysics: A tutorial. *Near-Surface Geophysics*.

