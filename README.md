# Untargeted Metabolomics Processing using MS-DIAL

MS-DIAL provides an easy-to-use pipeline for untargeted metabolomics.
Here, you will learn the process for analyzing your raw LC-MS/MS data and exporting it for downstream analysis and annotation.

## Requirements

Windows-based computer.
As MS-DIAL version 5.5, it is no longer a requirement to convert your vendor (.RAW) LC-MS/MS files into open source format (.MZML, .ABF); you don't need to use other programs to perform file conversion, such as Proteowizard.

**1. Download [MS-DIAL](https://github.com/systemsomicslab/MsdialWorkbench/releases) software for Windows from the official repository. Try downloading the latest version.**

<img width="474" height="430" alt="Screenshot 2025-11-10 195154" src="https://github.com/user-attachments/assets/87e99aad-2a1e-4f28-8316-44ce4b937aaf" />

It's the heavier version.

<img width="995" height="463" alt="Screenshot 2025-11-10 195303" src="https://github.com/user-attachments/assets/d57851c9-41c3-4ca2-8284-8390700b3ffa" />


**2. After downloading, you need to decompress the ZIP file.**

<img width="570" height="357" alt="Screenshot 2025-11-10 195928" src="https://github.com/user-attachments/assets/480e10e4-a3bc-450d-a633-41a80a76fd7e" />


**3. Also, you need to have all your LC-MS/MS files in a single folder.**
```text
.
├── project_folder
│   ├── file1_Sample1.RAW
│   └── file2_Sample2.RAW
│   └── file3_Blank.RAW
└── Documents
```

<img width="531" height="370" alt="Screenshot 2025-11-10 200753" src="https://github.com/user-attachments/assets/1069b2ec-5b04-403e-9de9-480393d7b70d" />

## Disclaimer

The instructions given here are for MS-DIAL version 5.

### Determine peak height and MS/MS cutoff

1. Start by opening the **RawDataViewer** tool. This step is essential to filter out background noise.

<img width="560" height="313" alt="Screenshot 2025-11-10 201753" src="https://github.com/user-attachments/assets/4170f0e5-2ff4-4c78-89f7-2cc0b6d61b95" />

2. A window will open; here, you have to set the path to your raw files. Click the Browse button to select the location of your files.

<img width="455" height="293" alt="Screenshot 2025-11-10 202032" src="https://github.com/user-attachments/assets/94eb84fd-7c81-4817-9fb8-12d18137ea09" />

3. Here you can select one file at a time. Once you have chosen the correct path for your files, select the ionization mode for your analysis (Positive or Negative).

4. Push the Load button to load the file into the program.

5. After loading, you need to left-click the file to ensure it opens (the file will have a blue shadow).

<img width="393" height="93" alt="Screenshot 2025-11-10 202431" src="https://github.com/user-attachments/assets/a53db900-18fc-4e99-aa19-ad8ee1cf629d" />

6. Click the Show button.

7. A new window will open where you can see three main windows, a histogram of peak height, MS, and MS/MS peak intensity information. This window also provides a table with details such as scan start time, polarity, MS levels, base peak m/z, and base peak intensity for each metabolite in your sample.

<img width="595" height="400" alt="Screenshot 2025-11-10 202920" src="https://github.com/user-attachments/assets/0da82d5f-d6f4-484f-89f1-5275a4078534" />

9. First, we need to watch the Histogram of peak height. The histogram illustrates how peaks are distributed across different peak height cut-offs, helping you identify the transition from noise to meaningful peaks. Peaks on the left side of the graph, often highlighted in blue, generally represent noise associated with a lower peak threshold. In contrast, the peaks on the right, highlighted in red, are more reliable and correspond to a higher threshold.

<img width="961" height="605" alt="Screenshot 2025-11-10 203509" src="https://github.com/user-attachments/assets/b19da03c-0571-46cd-9a29-047f12e1a0c3" />

The peak height indicated by the arrow corresponds to the higher-numbered peak and could be a good starting point for the **Peak Height** field in MS-DIAL.

12. Something similar occurs for the Histogram of the MS2 spectrum intensity. These are the significant features marked in red.

<img width="460" height="135" alt="Screenshot 2025-11-10 203807" src="https://github.com/user-attachments/assets/272a026e-aabf-4d3c-9327-a8b5dfdf5632" />

Equally, the red arrow indicates the higg-numbered counts in that spectrum intensity and could be a good starting point for the **MS/MS abundance cut off** field in MS-DIAL.

13.  Once you have selected the proper number for the **Peak Height** and **MS/MS abundance cut off**, you can close the RawDataViewer tool.

14. **Important**: Determine the Peak height and MS/MS abundance cut-off only for your samples or QCs, not for your blanks.

### Start up a project

Begin by opening MS-DIAL and starting a new project using the icon in the centre of the screen.

MS-DIAL will prompt you to enter a `Project title` and a `Project file path`. Please remember that the project file path must contain all of your raw LCMS files &ndash; you can navigate to this folder using the `'Browse'` button.

It is recommended that you change the default `.mdproject` file name generated by MS-DIAL to something more easily recognisable in the future,
such as `date_sampletype_ionisationmode.mtd`.

