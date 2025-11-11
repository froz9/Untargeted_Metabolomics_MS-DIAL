# Untargeted Metabolomics Processing using MS-DIAL

MS-DIAL provides an easy-to-use pipeline for untargeted metabolomics.
Here, you will learn the process for analyzing your raw LC-MS/MS data and exporting it for downstream analysis and annotation.

## Requirements

Windows-based computer.
As MS-DIAL version 5.5, it is no longer a requirement to convert your vendor (.RAW) LC-MS/MS files into open source format (.MZML, .ABF); you don't need to use other programs to perform file conversion, such as Proteowizard.

1. **[MS-DIAL](https://github.com/systemsomicslab/MsdialWorkbench/releases) software for Windows needs to be downloaded from the official repository. Try downloading the latest version.**

<img width="474" height="430" alt="Screenshot 2025-11-10 195154" src="https://github.com/user-attachments/assets/87e99aad-2a1e-4f28-8316-44ce4b937aaf" />

It's the heavier version.

<img width="995" height="463" alt="Screenshot 2025-11-10 195303" src="https://github.com/user-attachments/assets/d57851c9-41c3-4ca2-8284-8390700b3ffa" />

2. **After downloading, you need to decompress the ZIP file.**

<img width="1139" height="713" alt="Screenshot 2025-11-10 195928" src="https://github.com/user-attachments/assets/480e10e4-a3bc-450d-a633-41a80a76fd7e" />

3. **Also, you need to have your LC-MS/MS files all present in a single folder.**
```text
.
├── project_folder
│   ├── file1_Sample1.RAW
│   └── file2_Sample2.RAW
│   └── file3_Blank.RAW
└── Documents
```

<img width="531" height="370" alt="Screenshot 2025-11-10 200753" src="https://github.com/user-attachments/assets/1069b2ec-5b04-403e-9de9-480393d7b70d" />


