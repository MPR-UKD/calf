# calf &nbsp;&nbsp;&nbsp;    ![cow-3357856_120](https://user-images.githubusercontent.com/3669480/196395829-4d63d17e-ba41-41d1-ae98-b3408c967dd6.jpg)

*calf* - <ins>**C**</ins>EST <ins>**a**</ins>nalysis software by <ins>**L**</ins>orentzian <ins>**f**</ins>itting

Welcome to calf, a user-friendly software for the analysis of chemical exchange saturation transfer (CEST) MRI data running on Windows 10/11. calf is developed in VC++ 2022 using MFC as graphical user interface. calf uses the control panels common in Windows, so that users can easily find their way around.

## Features
**calf** has several features that make it a useful tool for CEST MRI data analysis. Some of these features include:

- Lorentzian fitting algorithm
- Graphical display of CEST spectra
- Intuitive graphical user interface
- Support for Windows 10/11

## Getting Started

**Note:** To open the help file, right-click on the calf.chm file, select Properties and then Unblock. (This is because Windows may block files downloaded with active fields).



To get started with calf, please follow these steps:

1. Download the latest release, zip file or the full repository of calf from the GitHub repository.
2. Unzip the downloaded file.
3. Open the unzipped calf folder and double-click on calf.exe to start the software.

![](assets/img_1.png)

4. Once you have launched calf, you can open the provided CEST data in the test_data folder by clicking on the "Load Nifti" button.
5. To perform a CEST analysis, click on the "CEST Analysis" button. This will initiate the Lorentzian fitting algorithm to fit the CEST spectrum of each pixel, and generate CEST maps.

![](assets/img_2.png)

6. Now you can customize the parameters of the Lorentzian fitting and calculate CEST maps

## Usage and Citation
If you use calf in your research or work, please cite our paper. For any questions or issues, please feel free to open an issue on the GitHub repository.

Paper: <https://link.springer.com/article/10.1007/s10916-023-01931-6>

doi: <https://doi.org/10.1007/s10916-023-01931-6>

## License
calf is distributed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Q&A

### How can I add more CEST pools in my analysis?

You can easily extend the CEST pulses and set other boundaries locally by downloading the Calf Zip. After extracting the files, you will find the cest.ini file where you can manually adjust the pools. Here's a brief explanation of how you can do this:

In the cest.ini file, you will see the following configuration:

```
6 - No. of Lorentzian components (max = 20)
-6.000000 ! 6.000000  - frequency range
0.400000 ! 0.500000 ! 1.000000 ! lower bound, amplitude, upper bound of #1 = H2O
-1.500000 ! 0.000000 ! 1.500000 ! lower bound, frequeny, upper bound of #1 = H2O
0.200000 ! 2.000000 ! 5.000000 ! lower bound, width, upper bound of #1 = H2O
...
```

To add more CEST components, you can simply adjust the number of Lorentzian components and define the parameters for the new components. For example, if you want to add a 7th component, first change the number of components:

`7 - No. of Lorentzian components (max = 23)`

Then, add the parameters for the new component below the existing ones:

```
0.000000 ! 0.050000 ! 0.150000 ! lower bound, amplitude, upper bound of #7 = NewComponent
-2.600000 ! -1.600000 ! -0.600000 ! lower bound, frequeny, upper bound of #7 = NewComponent
0.200000 ! 2.000000 ! 5.000000 ! lower bound, width, upper bound of #7 = NewComponent
```

After making these changes, save the cest.ini file and the software should now include your new CEST component. You can also delete pools in the same way.

