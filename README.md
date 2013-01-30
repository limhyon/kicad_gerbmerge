kicad_gerbmerge
===============

Steps
1. Create Gerbers from KiCad.
2. Create Drill file with settings -
# Drill Units: inches
# Zeros Format: supress leading zeros
# Precision: Either 2.3 or 2.4
# Drill Origine: Absolute
# Drill Sheet: None
# Mirror Y Axis: OFF
# Minimal Header: ON Drill file from KiCad with following settings -
(reference: http://forum.sparkfun.com/viewtopic.php?t=1980 )

- the .drl file produced by these settings is acceptable to gerbv, and shows out
correctly, however editing this file is required for it to work with GerbMerge
as follows.

* Edit the excellon (.drl) file
(Comment : I'm not sure why G90 does not required. But, currently, it works)
(a) to remove code: G05
after first % and before T01
(b) to remove: T0
before the the M30, which is at the end of file.