# Freebody_loads_extractor

## About

This is a simple program developed to help stress engineers when post-processing results with the Freebody Loads Tool in MSC.Patran. It also features a GUI for a rapid deployment and execution of task. I have uploaded an executable `FLEX.exe` that you can download and run without the need of a compiler, it was created using  `pyinstaller` wtih the source code .py file.

## Freebody Loads Tool 

In the preliminary design phase of an aircraft the stress engineers usually compile a GFEM (Global Finite Element Model) to do a preliminary analysis on the response of the structure at certain loads. The GFEM can't offer accurate results for stress and strains but can give good results for load paths and forces acting on element nodes. These forces are used in the verification and sizing of the aircraft structural components such as spars, stringers, frames, etc.

For MSC.Patran users, the software has a post-processing tool for creating Freebody plots from Nastran results data. To use it the user need to request the calculation of the Grid Point Force Balance  for all the nodes in the model, this is done by adding the  `GPFORCE=ALL` in the case control section of the Nastran deck.

The engineer takes a section where he wants to extract force and moments, he selects the elements from the section and the nodes from which the forces will be extracted. A summation point is given, usually the center of gravity of the section, in which the forces and moments from the nodes will be summed, also a coordinate frame could be provided if the user wants to get the forces in a certain direction.

- picture here

In the case of an aircraft there are hundreds of load cases for which calculations are performed, these include crash loads, landing conditions and flight maneuvers loads. Because of the high number of sections and load cases, a lot of data will be generated for processing. Patran can output a .dat file for each section, in which for every load case we obtain the forces/moments at each node in the section and the forces/moments in the summation point at the Totals line in the .dat file.

- picture here

## FLEX

The Freebody Loads Extractor takes the .dat file, extracts the values from the file and writes and excel file with al the results ordered by loadcase, section and force/moment type.

## Next

For future work I plan to implement more features. Some of them are (and the list is open):
[] make a better GUI, improve design
[] implement feature that displays what .dat files the user has selected
[] implement feature that allows user to order the extracted data for specified load cases
[] use Patran_Command_Language (PCL) to give option of extraction data from sections without opening Patran, just by specifying elements, nodes, summation points and coordinate frames
[] ...