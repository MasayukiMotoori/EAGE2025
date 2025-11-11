**1D inversion of time-domain electromagnetic data with induced
polarization effects for a sea-floor hydrothermal deposit**

**Masayuki Motoori¹², Lindsey J. Heagy¹, Gosuke Hoshino², Kunihito Yamamoto², Haruhisa Morozumi², Kunpei Nagase², Shingo Sugimoto²**  
¹ University of British Columbia Geophysical Inversion Facility  
² Japan Organization for Metals and Energy Security (JOGMEC)


**Summary**

Seafloor hydrothermal deposits are polymetallic massive sulfide ore
deposits formed by the precipitation of metal components contained in
hot water ejected from the seafloor. The sea depth is 700- 2000m. Ore
bodies extend hundreds of meters horizontally and tens of meters
vertically. Ore bodies are exposed on the sea floor. Some lab-based
petrophysics study indicates that resistivity and chargeability are
diagnostic physical properties, even compared with seawater (3.0-3.5
S/m). Time-domain electromagnetic methods (TEM) are sensitive to
variations in resistivity. WISTEM (Waseda integrated seafloor
time-domain electromagnetic exploration) surveys have been conducted in
several areas. Negative transients, which are due to induced
polarization effects (IP), have been observed for data collected over
known deposits. It is important to understand the system response to
invert these data. The pressure vessel (PV), which contains the
transmitter and receivers, can impact the data. We use numerical
simulations to quantify these effects, and we develop a workflow for
estimating a linear filter which captures the effects of the PV. This
filter will then be used in subsequent simulations and inversions.
Finally, we perform one-dimensional time-domain IP inversion of the
field data. The estimated resistivity and IP parameters agree with
physical property measurements from the area.

**Background**

Seafloor hydrothermal deposits are polymetallic massive sulfide ore
deposits formed by the precipitation of metal components contained in
hot water ejected from the seafloor (JOGMEC, 2020). The depth of the sea
in the regions where these deposits are found ranges from 700-2000m. The
ore bodies extend hundreds of meters horizontally and tens of meters
vertically and are exposed on the sea floor (Morozumi et al., 2020). A
lab-based petrophysics study indicates that resistivity and
chargeability are diagnostic physical properties, with the hydrothermal
deposits expected to be more conductive and more chargeable than
seawater and host rock (Nakayama et al., 2012). Time-domain
electromagnetic methods (TEM) are sensitive to variations in
resistivity. The WISTEM (Waseda integrated seafloor time-domain
electromagnetic exploration system) has been proven to be effective, and
surveys have been conducted in several areas (Nakayama and Saito, 2016).
Some "fixed type" measurements are collected when the WISTEM system is
landed on the seafloor. In this type of measurement, negative
transients, due to induced polarization effects (IP), have been observed
for data collected over known deposits (Nakayama, Motoori, Saito, 2019).
The survey we will focus on was conducted by JOGMEC in the Okinawa
Trough in 2018. IP effects are particularly relevant when chargeable
materials, namely sulfides, are present. Motoori and Heagy (2024)
simulated and illustrated field plots about negative transients due to
the IP effect, performed a 1D synthetic study and showed sensitivity to
all IP parameters.

In order to invert data collected in the field, it is important to
understand the system response and be able to simulate it numerically,
The WISTEM system utilizes a 3.5-meter square loop for the transmitter
loop and a five-turn coincident-type receiver loop. Equipment like the
transmitter and the receiver is placed in the center of the loop, and
this can affect the data. "Reference measurements" where WISTEM measures
at a height of 100m above the seafloor are used for estimating the
system response. In this study, we first perform a simulation to study
the effect of the pressure vessel using the two-dimensional cylindrical
in SimPEG (Cockett, 2015; Heagy, 2017) and simpegEMIP (Kang, 2016).
Second, we deconvolve reference data with the analytical response of
seawater to obtain a linear filter that captures the system response.
This filter will then be used in subsequent simulations and inversions.
Finally, we perform a one-dimensional IP inversion using Empymod
(Werthmüller, 2017) with the fixed-type data containing negative
transients.

**Simulating pressure vessel impacts**

The transmitter current is a rectangular waveform with a certain ramp
time. The amplitude is 120 A, the base frequency is 0.125 Hz, and the
duty ratio is 5%, so the on-time is 200 msec. The receiver utilizes
24-bit A/D resolution and a sampling rate of 50 kHz. WISTEM is towed by
a Remotely Operated Vehicle (ROV) during the reference measurement. The
pressure vessel (PV) is made of aluminum, which is conductive but
non-magnetic.

For numerical simulations, we use SimPEG and simpegEMIP, which employ
the finite volume method in space and the backward Euler method in time.
To describe the IP effects, we refer to the chargeable model in the
following Pelton et al. (1978).

![A black text on a white background AI-generated content may be
incorrect.](./media/image1.jpg){width="4.1331856955380575in"
height="0.6786450131233596in"}

This study aims to test if a linear filter can capture the PV effect. We
consider four models: 1) Whole Space Seawater Response, 2) Seawater and
PV, 3) Target layer, 4) Target layer with PV. The geometry and physical
properties of the PV and target layer are shown in Figure 1. We obtain a
linear filter by deconvolving the data obtained from the simulation of
model 1 from the data obtained when simulating model 2. Then, we apply
the acquired filter to the data from model 3 and compare those to the
data from model 4. If the results align well, the linear filter is
considered effective. The results and models of our simulations are
shown in Figure 1. Figure 1a indicates that the deconvolved linear
filter acts as a smoothing filter, representing an additional current
waveform that persists after the transmitter. The filter applied to
model 3 agrees well with the simulated data for model 4, as shown in
Figure 1b. This demonstrates that the deconvolved linear filter captures
the PV effect effectively, enabling 1D simulation using the filter.

![A close-up of a diagram AI-generated content may be
incorrect.](./media/image2.jpeg){width="6.133333333333334in"
height="2.797267060367454in"}

***Figure 1** Simulation on Pressure vessel (PV) effect: (A) Acquired
filter from models 1 and 2, (B) Test of the filter on model with IP.*

**Processed Data and Filter Acquisition**

Now, we turn our attention to the field data shown in Figure 2. The ramp
time is 260 μsec. To estimate the linear filter, we first simulate the
step-off response with a 200 kHz sampling rate. We then apply a low-pass
filter with a 25 kHz cut-off frequency, which is based on the Nyquist
frequency of the A/D converter. Second, we deconvolve a linear filter
from reference data. We apply a Tikhonov inversion to stabilize the
filter derivation.

![A group of graphs showing different types of data AI-generated content
may be incorrect.](./media/image3.jpg){width="6.16535542432196in"
height="3.702341426071741in"}

***Figure 2** Processed data and filter acquisition. (A) Processed fixed
type data, (B) Processed reference measurement data, (C) Comparison
between simulations of a whole-space seawater model with the filter
applied and the field reference data. (D) Filters acquired using
deconvolution and Tikhonov inversion*

Both the field data and the data obtained from simulations are averaged
using the same windows. The results of our data processing and filter
acquisition are shown in Figure 2. The acquired filter appears
reasonable when compared with the previous simulations.

**1D inversion using the acquired filter**

To invert the fixed-type data, we used a five-layer model. Each layer
includes four IP parameters. The time constant τ, and the exponent C are
assumed to be common across all layers. The seawater layer is fixed at a
conductivity value of 0.304 (Ω·m) as measured using the CTD
(Conductivity, Temperature, and Depth sensor) attached to the ROV. The
inversion is performed using L2 norms for smallness and smoothness
regularization terms and Gauss-Newton optimization (Oldenburg and Li,
2005). We use Empymod for the forward simulation. The Jacobian matrix is
approximated using finite differences.

![A group of graphs showing different types of data AI-generated content
may be incorrect.](./media/image4.jpg){width="6.26875in"
height="3.104861111111111in"}

***Figure 3** Synthetic Study using the acquired filter.*

![A group of graphs showing different types of data AI-generated content
may be incorrect.](./media/image5.jpg){width="5.963252405949256in"
height="2.9555325896762903in"}

***Figure 4** Inversion of fixed-type data collected by WISETEM in 2018
at the Okinawa Trough*

To assess what we can expect to recover in the inversion, we first
conduct a synthetic study using a chargeable target layer of 20m
thickness and with the parameters; ρ~0~: 0.08 (Ω·m), η: 0.45, τ:
1.35×10⁻³ (sec), C: 0.7. The results are shown in Figure 3. We can see
that there is a low resistivity and high changeability target
concentrated in the shallow layers, where the sensitivity is the highest
compared to the true model.

We then apply our inversion workflow to the fixed-type data collected
with the WISTEM system in 2018. The results are shown in Figure 4. The
data are fit adequately, and the model recovers a conductive, chargeable
target near the seafloor. The model resembles that obtained in the
synthetic study, and the recovered physical property values are within
the expected range based upon physical property measurements.

**Discussion and Conclusion**

We inverted inductive-source marine TEM data that included IP effects.
Using deconvolution, we obtained a linear filter which captures the
conductive pressure vessel. The inversion successfully recovered IP
parameters within the expected ranges from the petrophysics study.
Non-uniqueness remains a significant challenge when estimating IP
parameters of deep structures. Chargeability has the effect of
decreasing resistivity at early times and increasing resistivity at late
times, making it difficult to distinguish between conductive shallow
layers and resistive deep layers. To address this issue, we plan to
investigate strategies for integrating geological and petrophysical
information.

**Acknowledgements**

The field data in this study were collected as part of projects
sponsored by the Manufacturing Industries Bureau, Ministry of Economy,
Trade and Industry (METI), Japan. We would like to acknowledge Dr. Keiko
Nakayama (GeoBless), Dr. Akira Saito (Emeritus Professor at Waseda
University) and Dr. Masashi Endo (RedStoneGEO) for their advice on
WISTEM.

**References**

Cockett, R., Kang, S., Heagy, L. J., Pidlisecky, A., & Oldenburg, D. W.
(2015). SimPEG: An open source framework for simulation and gradient
based parameter estimation in geophysical applications. Computers &
Geosciences, 85, 142--154.

Heagy, L. J., Cockett, R., Kang, S., Rosenkjaer, G. K., & Oldenburg, D.
W. (2017). A framework for simulation and inversion in electromagnetics.
Computers & Geosciences, 107, 1--19.

JOGMEC Conducts World's First Successful Excavation of Cobalt-Rich
Seabed in the Deep Ocean;Excavation Test Seeks to Identify Best
Practices to Access Essential Green Technology Ingredients While
Minimizing Environmental Impact: News Releases \| Japan Organization for
Metals and Energy Security (JOGMEC). (n.d.). Retrieved April 3, 2025,
from https://www.jogmec.go.jp/english/news/release/news_01_000033.html

Kang, S., & Oldenburg, D. W. (2016). On recovering distributed IP
information from inductive source time domain electromagnetic data.
Geophysical Journal International, 207(1), 174--196.

MOROZUMI, H., WATANABE, K., SAKURAI, H., HINO, H., KADO, Y., MOTOORI,
M., & TENDO, H. (2020). Additional information for characteristics of
seafloor hydrothermal deposits investigated by JOGMEC. Shigen-Chishitsu,
70(2), 113--119.

Motoori, M., & Heagy, L. J. (2024). A synthetic study investigating
induced polarization effects on time-domain electromagnetic data for
Sea-floor hydrothermal deposit. AGU24.

Nakayama, K., Moroori, M., & Saito, A. (2019). Application of
Time-Domain Electromagnetic Survey for Seafloor Polymetallic Sulphides
in the Okinawa Trough. 25th European Meeting of Environmental and
Engineering Geophysics, 1--5.

Nakayama, K., & Saito, A. (2016). Practical marine TDEM systems using
ROV for the ocean bottom hydrothermal deposits. 2016 Techno-Ocean
(Techno-Ocean), 643--647.

NAKAYAMA, K., YAMASHITA, Y., YASUI, M., YAMAZAKI, A., & Akira, S.
(2012). Electric and magnetic properties of the sea-floor hydrothermal
mineral ore deposits for the marine EM explorations. Proceedings of the
SEGJ Conference, 126, 162--165.

Oldenburg, D. W., & Li, Y. (2005). Inversion for Applied Geophysics: A
Tutorial. In Near-Surface Geophysics. Society of Exploration
Geophysicists.

Pelton, W. H., Ward, S. H., Hallof, P. G., Sill, W. R., & Nelson, P. H.
(1978). MINERAL DISCRIMINATION AND REMOVAL OF INDUCTIVE COUPLING WITH
MULTIFREQUENCY IP. GEOPHYSICS, 43(3), 588--609.

Werthmüller, D. (2017). An open-source full 3D electromagnetic modeler
for 1D VTI media in Python: Empymod. GEOPHYSICS, 82(6), WB9--WB19.
