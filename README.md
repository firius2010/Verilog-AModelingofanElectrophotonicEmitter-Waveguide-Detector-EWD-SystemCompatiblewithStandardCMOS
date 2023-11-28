# Verilog-A Modeling of an Electrophotonic Emitter-Waveguide-Detector (EWD) System Compatible with Standard CMOS Technology
![imagen Abstract](https://github.com/firius2010/Verilog-AModelingofanElectrophotonicEmitter-Waveguide-Detector-EWD-SystemCompatiblewithStandardCMOS/assets/17171888/9771bd67-cd61-4f36-85ff-b962834feb2c)
This repository contains resources and code associated with the manuscript titled "Verilog-A Modeling of an Electrophotonic Emitter-Waveguide-Detector (EWD) System Compatible with Standard CMOS Technology," published in IEEE Latin America Transactions.

## Repository Organization

This repository is organized as follows:

1. **Lookup Tables Data:** This folder contains the TXT files containing the data for the lookup tables used by the models.

2. **Cadence Environment Import File:** This folder contains the file to be imported into the respective Cadence environment.

## Requirements

The simulations in this repository were conducted using Cadence IC 5.0.33. It's worth noting that this version was chosen due to the availability of process models specific to the technology currently used for manufacturing these devices. The required process models and associated tools are only compatible with Cadence IC 5.0.33.

Please ensure you have access to Cadence IC 5.0.33 or a compatible version to run the simulations and utilize the provided files effectively.

## Library Import Instructions

To import the library into your Cadence environment, follow these steps:

1. Extract the contents of the file: "ElectrophotonicMacromodels.tar.gz" into the current working directory of your respective Cadence environment.

2. Locate the "cds.lib" file in your working directory and add the following line:
DEFINE ElectrophotonicMacromodels path_to_the_recently_extracted_folder

Replace "path_to_the_recently_extracted_folder" with the actual path to the folder you extracted in step 1.

3. After completing step 2, you'll also need to edit the "disciplines.vams" file in your Cadence environment by adding the following lines:

```verilog
// Optical
nature Optical
    units      = "W";
    access     = OptPwr;
    abstol     = 1e-12;
endnature

// Conservative discipline
discipline optical
    potential    Optical;
enddiscipline
```

These lines define the optical nature and discipline settings required for the simulation. Be sure to add these lines to your "disciplines.vams" file as specified to ensure proper simulation behavior.

4. Restart your Cadence session if it was already initiated.

These steps will ensure that the library is properly imported and accessible within your Cadence environment.
