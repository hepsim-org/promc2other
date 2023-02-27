Convertor: ProMC to LCIO/StdHep
S.Chekanov (ANL)
----------------------

source setup.sh
javac promc2lcio.java
javac promc2stdhep.java


Usage:
java promc2lcio file.promc file.slcio
java promc2stdhep file.promc file.stdhep

# print event 40
java LCTExpanded file.slcio 40

Full example:
wget http://mc.hep.anl.gov/asc/hepsim/events/pp/100tev/higgs_ttbar_mg5/mg5_Httbar_100tev_001.promc
java promc2lcio mg5_Httbar_100tev_001.promc mg5_Httbar_100tev_001.slcio
java LCTExpanded mg5_Httbar_100tev_001.slcio 10 # print event 10

