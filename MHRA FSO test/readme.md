# FSO Test
Run example: `./RDFox sandbox . ./fso-test.script`

This script includes methods that imports some FSO triples and saturates the graph. It reads from the directory `MHRA FSO test`.

### Standard units used
Temperature     degC
Length          m
Area            m2
Volume flow     m3/h
Velocity        m/s
Power           W
Density         kg/m3

### Calculations
1. Temperature difference over each terminal inferred from system properties (`ex:fluidTemperatureDifference`) [degC]
1. Flow demand for each terminal derived from power demand and temperature difference using simple formula (`ex:terminalVolumeFlow`) [m3/s]
1. Transitivity to `fso:suppliesFluidTo` for all components that are supplied further out in the tree (`ex:indirectlySuppliesFluidTo`)
1. Segment flow as a sum of the `ex:terminalVolumeFlow` of all terminas that are indirectly supplied by the segment (`ex:segmentVolumeFlow`) [m3/s]
1. Inner pipe cross sectional area from inner pipe diameter (`ex:innerCrossSectionalArea`) [m2]
1. Fluid velocity at segment level based on cross sectional area and segment volume flow (`ex:fluidVelocity`) [m/s]