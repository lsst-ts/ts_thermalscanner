# cRIO Based Thermal Scanner

This software readouts and store data from (M1M3's) cRIO based thermal scanner
modules.

## LabVIEW application

FPGA module and Real-Time .vi are included. As Thermal Scanner is using
extension boards, the real-time part can run only on a computer not - it
cannot run on the RIO. You can start FPGA application and see updated front
panel, or start real-time application, which allows capturing date to a CSV
file.

The application is designed in LabVIEW 2023 Q3. It needs FPGA module and
Real-Time module to run.
