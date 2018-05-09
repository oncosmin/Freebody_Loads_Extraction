# Freebody_loads_extractor

This is a simple program developed to help stress engineers when post-processing results with the Freebody Loads Tool in MSC.Patran. It also features a GUI for a rapid deployment and execution of task. I have uploaded an executable `FLEX.exe` that you can download and run without the need of a compiler, it was created using  `pyinstaller` wtih the source code flex.py file.

When using the Freebody Load Tool from MSC.Patran the user has the option of exporting the section forces and moments by generating a report .dat file. Once you have created .dat files for all of the necessary sections, open Flex.exe and by using the browse option you have the capability of selecting all of the .dat files, after the file selection hit the Run button. The program will process all the .dat files and will create a Results.xls file where for every section a worksheet will be created with the name of the .dat file and will contain all the results in order of the load cases and force/moment type.

For more informations about how the program works, check the [wiki page](https://github.com/oncosmin/Freebody_Loads_Extraction/wiki/Welcome-to-the-Freebody_Loads_Extraction-wiki!).

For future work I plan to implement more features. Some of them are (and the list is open):

- [ ] make a better GUI, improve design
- [ ] implement feature that displays what .dat files the user has selected
- [ ] implement feature that allows user to order the extracted data for specified load cases
- [ ] use Patran_Command_Language (PCL) to give option of extraction data from sections without opening Patran, just by specifying elements, nodes, summation points and coordinate frames
- [ ] ...