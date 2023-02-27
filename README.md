# Converter: ProMC to LCIO/StdHep files

This converter allows you to convert ProMC archive files from the HepSim Monte Carlo repository 
with events from Monte Carlo generators to LCIO/StdHep files. To compile this converter, you need Java JDK.


## Compilation

```
source setup.sh
javac promc2lcio.java
javac promc2stdhep.java
```

## Usage:

```
java promc2lcio   file.promc file.slcio
java promc2stdhep file.promc file.stdhep
```

Here is a full example:

Get a ProMC file from the HepSim:

```
wget https://mc.hep.anl.gov/asc/hepsim/events/mumu/250gev/pythia8_higgs_bbar//gev250mumu_higgs_bbar_001.promc
```

This file contains Monte Carlo events with Higgs decaying to b-jets at e+e- collider at 250 GeV. Now you can explore the events in this file as :

```
java -jar lib/browser_promc.jar gev250mumu_higgs_bbar_001.promc
```

Now let's do the conversions:

```
file="gev250mumu_higgs_bbar_001"
java promc2stdhep ${file}.promc ${file}.stdhep
java promc2lcio   ${file}.promc ${file}.slcio 
```
The converted files with the extensions stdhep and slcio can be used by the external programs. You can look at the LCIO event 10 as:

```
javac LCTExpanded.java
java LCTExpanded  ${file}.slcio  10 
```

Other converters (implemented in C++) can be found in the ProMC package (https://atlaswww.hep.anl.gov/asc/promc/)

S.Chekanov (ANL)
