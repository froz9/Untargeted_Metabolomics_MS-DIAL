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

9. First, we need to watch the Histogram of peak height. The Histogram illustrates how peaks are distributed across different peak height cutoffs, helping you identify the transition from noise to meaningful peaks. Peaks on the left side of the graph, often highlighted in blue, generally represent noise associated with a lower peak threshold. In contrast, the peaks on the right, highlighted in red, are more reliable and correspond to a higher threshold.

<img width="481" height="303" alt="Screenshot 2025-11-10 203509" src="https://github.com/user-attachments/assets/b19da03c-0571-46cd-9a29-047f12e1a0c3" />

The peak height indicated by the arrow corresponds to the higher-numbered peak and could be a good starting point for the **Peak Height** field in MS-DIAL.

12. Something similar occurs for the histogram of the MS2 spectrum intensity. These are the significant features marked in red.

<img width="460" height="135" alt="Screenshot 2025-11-10 203807" src="https://github.com/user-attachments/assets/272a026e-aabf-4d3c-9327-a8b5dfdf5632" />

Equally, the red arrow indicates the higher-numbered counts in that spectrum intensity and could be a good starting point for the **MS/MS abundance cut off** field in MS-DIAL.

13.  Once you have selected the proper number for the **Peak Height** and **MS/MS abundance cut off**, you can close the RawDataViewer tool.

14. **Important**: Determine the Peak height and MS/MS abundance cutoff only for your samples or QCs, not for your blanks.

### Start up a project

1. Start by opening MS-DIAL and starting a new project using the icon in the centre of the screen.

2. MS-DIAL will prompt you to enter a `Project title` and a `Project file path`. Please remember that the project file path must include all your raw LC-MS/MS files; you can navigate to this folder using the `'Browse'` button.

3. It is recommended that you change the default `.mdproject` file name generated by MS-DIAL to something more easily recognisable in the future, such as `date_sampletype_ionisationmode.mtproject`.
<img width="797" height="399" alt="Screenshot 2025-11-10 210115" src="https://github.com/user-attachments/assets/86398837-3e88-4510-8c06-30e803dd0e4f" />

4. After setting everything. Click the `Next` button.

### Measurement parameters

5. The next screen will ask you to define your `'Analysis file paths'`. Click the `Browse` button, then select all your LC-MS/MS files.
**Note that these must be in the same folder as your project to be valid. If you can't see your files, check the correct extension in the bottom right corner**

<img width="795" height="395" alt="Screenshot 2025-11-10 210809" src="https://github.com/user-attachments/assets/afe61a79-d474-4f13-9dfe-5586fe7a97fe" />

6. Once you have done this, you will need to change the `'Type'` column to indicate whether that sample is a sample, blank, QC, or standard.

<img width="799" height="405" alt="Screenshot 2025-11-10 210957" src="https://github.com/user-attachments/assets/1b6b6c48-9c70-4339-96c1-621a03242612" />

**It is also recommended, for quick analysis later on, to change the values in the `'Class ID'` column. For example, in the `'Class ID'` column below, it is indicated what the sample type is (if you have multiple groups, you can specify these here)**

<img width="802" height="398" alt="Screenshot 2025-11-10 211245" src="https://github.com/user-attachments/assets/afab4958-0058-45bd-91f8-df6a7469840d" />

7. It is essential to set the Acquisition type based on your data characteristics, for the **`Microbial Natural Products Research Lab Chemistry Faculty, UNAM`**. The data was acquired in DIA mode, so click the `DDA` button to display the list of options, then select AIF.
8. Click the `Set to all` button.

<img width="804" height="400" alt="Screenshot 2025-11-10 212202" src="https://github.com/user-attachments/assets/4e90e93f-3398-4372-953b-8a0fd5d25f37" />

10. Once you have finished, click `'Next'` to continue.

<img width="796" height="399" alt="Screenshot 2025-11-10 212314" src="https://github.com/user-attachments/assets/c58e7d6a-8510-4f5d-8cd1-ac024365b65d" />

### Measurement parameters

11. The next screen will ask you to select various parameters regarding how your data was acquired.

Firstly, you can define a project name. It is recommended that you change the default `.mddata` file name generated by MS-DIAL to something more easily recognisable in the future, such as `\date_sampletype_ionisationmode.mtd`.

**For our purposes, most of the default options will be appropriate. **

- Data type for both `MS1` and `MS2` should be set to `Centroid data` for our data, acquired using a Q-Exactive LC-MS/MS apparatus.
- Ensure you choose the correct `'Ion mode'` at the bottom left, either positive or negative ionisation. And that you select the correct `'Target omics'` from either metabolomics or lipidomics.

12. For the **`Microbial Natural Products Research Lab Chemistry Faculty, UNAM`**, your window needs to look like this:

<img width="644" height="402" alt="Screenshot 2025-11-10 213353" src="https://github.com/user-attachments/assets/06861aa1-2a0a-4685-ada5-e96c32cd50bb" />

13. Click `Next` once complete.

## Analysis parameter settings

### Data collection

_If you have a parameter configuration file, you can load it in via the `Load parameter` button in the bottom-left of the window._

We begin setting analysis parameters by entering the data collection parameters.

**Mass Accuracy:**

|               | Metabolomics |
|---------------|--------------|
| MS1 tolerance | 0.01 Da      |
| MS2 tolerance | 0.025 Da     |

- Justification for the MS1 Tolerance: The Q Exactive Plus instrument consistently provides precursor mass accuracy of less than 3 ppm. Setting a tight tolerance here is essential to leverage this capability. A window of **0.01 Da** is narrow enough to specifically exclude the vast majority of incorrect candidates from even being considered for an MS/MS match.
- Justification for the MS2 Tolerance: This value (**0.025 Da**) is recommended in the official MS-DIAL tutorials and represents an ideal balance for Orbitrap MS/MS data. While still highly accurate, MS/MS scans can have slightly lower mass precision than MS1 scans due to lower ion statistics for individual fragments.

**Data collection parameters:**

These parameters are displayed if you click the `Advanced` button. **For our purposes, most of the default options will be appropriate. **

|                        | Metabolomics |
|------------------------|--------------|
| Retention time begin   | 0 min        |
| Retention time end     | 100 min      |
| MS1 mass range begin   | 0 Da         |
| MS1 mass range end     | 0000 Da      |
| MS/MS mass range begin | 0 Da         |
| MS/MS mass range end   | 2000 Da      |
| Execute retention time correction | FALSE||

*You can choose here to perform retention time correction. This should be set to FALSE otherwise, and set to FALSE if you do not have information about the analytical order of your samples.*

**Isotope recognition:**

|                             | Metabolomics |
|-----------------------------|--------------|
| Maximum number of isotopes  | 2            |
| Maximum charged number      | 2            |
| Consider Cl and Br elements | FALSE        |

**Multithreading (will depend on your machine):**

If your computer is a recent model, you can select more than 4, depending on your processor.

|                                    | Metabolomics |
|------------------------------------|--------------|
| Number of threads                  | 8            |

Click `Next` once complete.

<img width="643" height="401" alt="image" src="https://github.com/user-attachments/assets/06ae13aa-9a00-45c9-94aa-b9283d255877" />

### Peak detection

Next, set the **`Minimum peak height`** threshold based on the value obtained from the [**RawDataViewer**](#determine-peak-height-and-MS/MS-cutoff) tool. Remember, MS-DIAL will not retain those peaks below this threshold.
For this example, a value of `524268` is the starting point. However, this will vary by your samples and may require data-dependent tuning.

Set the `'Mass slice width'` value to the default, along with all options in the drop-down `'Advanced'` menu.

|                     | Metabolomics |
|---------------------|--------------|
| Minimum peak height | 100000       |
| Mass slice width    | 0.05 Da      |



