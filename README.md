# cRIO Based Thermal Scanner

This software readouts and store data from (M1M3's) cRIO based thermal scanner
modules.

## LabVIEW application

FPGA module and Real-Time .vi are included. As Thermal Scanner is using
extension boards, the real-time part can run only on a computer not - it
cannot run on the RIO. You can start FPGA application and see updated front
panel, or start real-time application, which allows capturing date to a CSV
file.

The application is designed in LabVIEW 2023 Q3. It needs FPGA module to run.

## Temperature conversion

Temperature conversion (from the thermocouples reported mV to degC) was taken
from the NI-9213 example, installed with LabVIEW. As thermocouples measure
relative temperature to the cold end, the absolute temperature is calculated
with relation to the cold-end temperature.

Autozero measurement is substracted from the measured values. Cold plate
readout value is converted to degrees C, that's converted to mV (using NIST K
thermocouples polynomials), and added to mV measured (actually measured +
autozero). The calculated mV is then converted (again using NIST polynomials)
to degC.

If "Captured" is activated in the LabVIEW control panel, the readout data
(together with timestamp) are logged into selected logging file.

:warning: The current setup works with a single module, and is essentially a prototype.
If that approach will be scalled, readouts from different modules and units
**must** be cross-calibrated  (due to different cold-end measurement error).
