# CARD-FD

## Class-Aware Reliability and Recipient-Deficiency-Aware Federated Distillation for Intrusion Detection

**Authors:** Truong Duc Duong, Tran Tuan Kiet, Nguyen Huu Quyen, and Pham Van-Hau.  
**Affiliation:** University of Information Technology, Vietnam National University Ho Chi Minh City.  
**Manuscript status:** submitted to SOICT 2026.

**[Download the full research materials from Google Drive](https://drive.google.com/drive/folders/1JpQNZV5AaicAjldENgG5P9i1FC5ZVVHo?usp=sharing)**  
[Project repository](https://github.com/huuquyen2606/CARD-FD-Public)

This README is the complete guide to the public resource index and the full research handover: what to download, where files belong, how to reproduce figures and tables, how to inspect or resume experiments, and how maintainers upload and verify the materials.

## Contents

1. [Project and distribution model](#project-and-distribution-model)
2. [Download and storage](#download-and-storage)
3. [Full handover layout](#full-handover-layout)
4. [Experiment inventory](#experiment-inventory)
5. [Data and preprocessing](#data-and-preprocessing)
6. [Reproduce figures and tables](#reproduce-figures-and-tables)
7. [Run or resume experiments](#run-or-resume-experiments)
8. [Interpretation and communication cost](#interpretation-and-communication-cost)
9. [Manuscript and workflow](#manuscript-and-workflow)
10. [Upload and verify the Drive handover](#upload-and-verify-the-drive-handover)
11. [Upload this index to GitHub](#upload-this-index-to-github)
12. [Troubleshooting](#troubleshooting)
13. [Verification and retention](#verification-and-retention)
14. [File inventory](#file-inventory)
15. [Publication and license](#publication-and-license)

## Project and distribution model

CARD-FD builds recipient-specific teachers using class-aware donor reliability and applies deficiency-aware distillation after sample-count-based parameter fusion. Experiments use CICIoT2023 with 34 classes and two federation configurations: 10 clients and 100 clients.

The comparison includes **FedAvg (PyTorch), FedALA, FedNH, FedPLVM, MP-FedCL, and CARD-FD**. The reported endpoint is **round 20**. Some saved sessions extend beyond this endpoint; those later rounds must not replace the paper's reported results.

| Location | Purpose | Included resources |
|---|---|---|
| This GitHub repository | Public project overview and resource directory | This single README, empty .gitkeep placeholders, existing LICENSE, and .gitignore |
| Full Source on Google Drive | Full research handover | Source notebooks, data partitions, checkpoint archives, logs, analysis scripts and inputs, outputs, and manuscript files |

Cloning this repository downloads the documentation index. The experiment and analysis files must be downloaded from Drive. All instructions for this public index are in this single README. Empty .gitkeep files preserve the resource directory structure in Git.

## Download and storage

1. Open the [Full Source Drive folder](https://drive.google.com/drive/folders/1JpQNZV5AaicAjldENgG5P9i1FC5ZVVHo?usp=sharing).
2. If a `CARD-FD-Handover` wrapper is present, open it. Locate `Full-Source/` and the handover README.
3. Choose the smallest set needed for your task:
   - **Read the paper:** `Full-Source/Paper/Submitted/CARD-FD.pdf`.
   - **Recreate figures/tables:** `Full-Source/Analysis/CARD_FD_analysis_handover.zip`.
   - **Run a method:** the notebook under `Experiment/<method>/<10C-or-100C>/`, its matching partition under `Data/`, and checkpoint archives if continuing or evaluating a saved run.
   - **Preserve the full study:** all handover files, including session logs and preprocessing information.
4. Extract into a dedicated working location; retain archive names and internal paths.
5. Check download integrity before depending on an archive or deleting another copy.

The inspected local handover occupied approximately **27.9 GB (26.0 GiB)** before extraction. Decompressed files require additional space. This is the full handover size, not the size of this GitHub index. The lightweight analysis ZIP is approximately 5.55 MB.

If Drive asks you to sign in or request access, follow its access process. The supplied link identifies the intended storage location; public accessibility and completion of every upload must be checked by the maintainers.

## Full handover layout

```text
CARD-FD-Handover/
├── README.md
└── Full-Source/
    ├── Analysis/
    │   ├── CARD_FD_analysis_handover.zip
    │   └── Statistic.zip
    ├── Data/
    │   ├── 10C/
    │   │   ├── data-preprocessing_10C.ipynb
    │   │   ├── data-preprocessing_10C_logs.log
    │   │   ├── Raw_10C.zip
    │   │   └── Review_data_10C.zip
    │   └── 100C/
    │       ├── data_preprocessing_100C.ipynb
    │       ├── data_preprocessing_100C_logs.log
    │       └── Raw_100C.zip
    ├── Experiment/
    │   ├── CARD-FD/
    │   ├── FedAvg/
    │   ├── FedALA/
    │   ├── FedNH/
    │   ├── FedPLVM/
    │   └── MP-FedCL/
    │       └── [each method has 10C/ and 100C/ subdirectories]
    └── Paper/
        └── Submitted/
            ├── CARD-FD.pdf
            └── Overleaf.zip
```

Directory names and capitalization above match this handover. Preserve them when moving files to a case-sensitive system.

## Experiment inventory

Every method has a notebook, checkpoint archive(s), and execution log(s) for both configurations.

| Method | 10-client notebook | 100-client notebook |
|---|---|---|
| CARD-FD | `Full-Source/Experiment/CARD-FD/10C/CARD-FD_10C.ipynb` | `Full-Source/Experiment/CARD-FD/100C/CARD-FD_100C.ipynb` |
| FedAvg | `Full-Source/Experiment/FedAvg/10C/FedAvg_10C.ipynb` | `Full-Source/Experiment/FedAvg/100C/FedAvg_100C.ipynb` |
| FedALA | `Full-Source/Experiment/FedALA/10C/FedALA_10C.ipynb` | `Full-Source/Experiment/FedALA/100C/FedALA_100C.ipynb` |
| FedNH | `Full-Source/Experiment/FedNH/10C/FedNH_10C.ipynb` | `Full-Source/Experiment/FedNH/100C/FedNH_100C.ipynb` |
| FedPLVM | `Full-Source/Experiment/FedPLVM/10C/FedPLVM_10C.ipynb` | `Full-Source/Experiment/FedPLVM/100C/FedPLVM_100C.ipynb` |
| MP-FedCL | `Full-Source/Experiment/MP-FedCL/10C/MP-FedCL_10C.ipynb` | `Full-Source/Experiment/MP-FedCL/100C/MP-FedCL_100C.ipynb` |

**FedAvg uses the PyTorch implementation associated with the updated paper results.** Historical workbooks may contain earlier FedAvg results; use the verified PyTorch records in the analysis package when reproducing the submitted tables and curves.

`CARe-FD`, `carefd`, and `CARD-FD` appear in historical filenames and run directories. The paper's displayed method name is **CARD-FD**. Preserve internal run names because notebooks and resume paths may depend on them.

### CARD-FD 100-client checkpoints

The 100-client run is stored in five independent session archives:

| Archive | Checkpoint rounds found in the archive |
|---|---|
| `CARD-FD_100C_checkpoint_R1.zip` | 1 |
| `CARD-FD_100C_checkpoint_R2_R6.zip` | 2-6 |
| `CARD-FD_100C_checkpoint_R7-R11.zip` | 7-11 |
| `CARD-FD_100C_checkpoint_R12_R16.zip` | 12-16 |
| `CARD-FD_100C_checkpoint_R17_R20.zip` | 17-20 |

These are separate ZIP archives, not multipart pieces of one ZIP. Each contains a run directory with the same name and session-specific metadata. **Extract each archive into its own destination directory** to preserve its logs, summaries, manifests, and checkpoints. Do not blindly merge the archives and overwrite identically named files.

Other checkpoint archives can also contain metrics, configuration files, preprocessing metadata, or caches in addition to model states. Check their contents before selecting an evaluation or resume file.

## Data and preprocessing

The experiments use CICIoT2023 with 34 classes and the feature configuration recorded in the notebooks and manifests.

Despite their filenames, **`Raw_10C.zip` and `Raw_100C.zip` contain exported client partitions and test data**, rather than an untouched copy of the upstream dataset:

- `Raw_10C.zip` contains `part_1.csv` through `part_10.csv` and `test_total.csv` at its archive root.
- `Raw_100C.zip` contains the partition export under `cic_iot_noniid_100/run_20260907T180249Z_immfyucm/`, including client files, `test_total.csv`, distribution statistics, and a manifest.
- `Review_data_10C.zip` contains `dataset_statistics_pivot.csv` and distribution images.
- The preprocessing notebooks and accompanying logs document how the partitions were produced. They retain the original Kaggle input paths; update these paths for another environment.

The two configurations use randomized, heterogeneous partitioning procedures; they are **not Dirichlet partitions**. Do not describe them using an invented Dirichlet concentration parameter. Consult the corresponding preprocessing notebook for the exact selection, allocation, and split logic; the 10-client and 100-client procedures are not identical.

For reproduction of the reported runs, prefer the saved partitions and the associated preprocessing metadata. Recreating a partition from the upstream data is a separate operation and must be checked against the archived counts and manifests.

CARD-FD reserves 340 calibration samples and 680 reference samples, with 10 and 20 samples per class, respectively. The distribution figure uses the original training counts **before** removing these shared pools. Keep the class order, feature order, and any saved preprocessing state consistent with the chosen checkpoint.

## Reproduce figures and tables

The lightweight analysis archive contains all inputs required for its saved-result calculations. No GPU or multi-gigabyte dataset extraction is needed for this workflow.

1. Extract `Full-Source/Analysis/CARD_FD_analysis_handover.zip` into a separate directory, for example `Full-Source/Analysis/Reproduction/`.
2. The extracted archive has its own `Full-Source/` wrapper. Open:

   ```text
   Full-Source/Analysis/Reproduction/Full-Source/analysis/
   ```

3. Pre-generated results are already available in `outputs/`. The commands and output mapping below provide the reproduction instructions; the archive also retains its original README as historical package documentation.
4. To regenerate the results, run the following commands from that extracted `analysis` directory on Windows:

   ```powershell
   python -m venv .venv
   .\.venv\Scripts\python.exe -m pip install -r requirements.txt
   .\.venv\Scripts\python.exe scripts/reproduce.py
   .\.venv\Scripts\python.exe scripts/verify_submission.py
   ```

   On Linux/macOS, use `python3 -m venv .venv` and `.venv/bin/python` for the remaining commands.

The verification script expects the PDF stored in the extracted archive's sibling `paper/submitted/` directory. Keep that wrapper and PDF in place. That archived PDF is byte-identical to `Full-Source/Paper/Submitted/CARD-FD.pdf` in this handover at the time this README was prepared.

| Paper item | Reproduction source | Main outputs inside the extracted `analysis/outputs/` |
|---|---|---|
| Figure 1: workflow | Editable `inputs/CARD_FD_Workflow.drawio` | `card_fd_workflow.png` |
| Figure 2: client training distributions | `scripts/plot_data_distribution.py` and original class-count CSV files | `data_distribution.pdf`, `data_distribution.png` |
| Figure 3: round-wise performance | `scripts/render_comparison.py` and per-round measurements | `learning_curves.pdf`, `learning_curves.png` |
| Table 1: round-20 performance | `scripts/reproduce.py` and saved metric evidence | `table1_performance_percent.csv`, `table1_performance.tex` |
| Table 2: communication cost | `scripts/reproduce.py`, model shapes, and prototype-count evidence | `table2_communication_display.csv`, `table2_communication.tex`, `communication_R20_by_setting.csv` |

Figure 1 is a manually editable workflow diagram, not a plot generated from experimental measurements. Open its `.drawio` source in diagrams.net to edit it.

The analysis package includes provenance records, checksums, and validation reports. Its checks matched 84 numerical cells in Table 1 and 13 displayed values in Table 2 to the supplied PDF. These are saved-evidence and arithmetic checks, not a rerun of model training or test-set inference.

`Statistic.zip` preserves historical and intermediate workbooks. Its `Save/` folder and files marked `Old` should not be treated as the authoritative submitted results. Use the analysis package's verified input records and output tables for the current paper.

## Run or resume experiments

The archived notebooks reflect Kaggle sessions and may already be configured to resume an existing run. There is no single shared training entry point for all methods.

1. Select a method and `10C` or `100C` configuration under `Full-Source/Experiment/`.
2. Extract the corresponding data archive into a known location.
3. Open the matching notebook and inspect its configuration and dependency cells before execution.
4. Update data paths such as `DATA_DIR` or `DATA_ROOT` to the extracted directory containing the expected client and test files.
5. Decide whether to start from scratch, evaluate a saved state, or resume training. Review variables such as `RESUME_CHECKPOINT`, `RESUME_FROM`, and `CHECKPOINT_INPUT_DIR`, where present. Follow that notebook's documented fresh-run or resume settings rather than assuming a shared switch across methods.
6. For a resumed run, select the checkpoint from the same method, client configuration, and session lineage. Restore additional state as required by that notebook; a global model weight file alone may not contain everything needed for an exact continuation.
7. Configure a writable output directory separate from the archived evidence, then execute the intended cells in order.
8. Compare round-20 outputs with the analysis package. Retain new-run outputs separately from the submitted-run artifacts.

Use the package versions, hardware information, seed settings, and configuration recorded by the selected experiment when available. A common software/hardware environment across all archived baseline sessions has not been established. The analysis package's `requirements.txt` and `environment_analysis.txt` describe figure/table reproduction, **not** the training environments.

## Interpretation and communication cost

- Results are reported at the fixed round-20 endpoint, not the best observed test round.
- CARD-FD metrics summarize post-distillation client models using an unweighted client mean. Baseline rows evaluate the corresponding global model or global body/prototype combination. These are different evaluation objects.
- The evidence comprises the supplied runs; do not interpret it as repeated-seed means or confidence intervals.
- Communication cost is a **logical tensor-value payload per client at round 20**, expressed in decimal kB (`1 kB = 1,000 bytes`). It is not measured network traffic, checkpoint file size, or an average over training rounds.
- Table 2 averages the per-client means of the 10-client and 100-client settings, except MP-FedCL download, which is shown separately for the two settings. It does not pool all 110 clients into one weighted mean.
- FedPLVM prototype counts vary across rounds; its round-20 counts must not be applied to every round.
- MP-FedCL download reflects the padded global prototype pool in the archived implementation and depends on the client count.
- Serialization, transport headers, and other excluded metadata are listed below under Communication formulas. Preserve these qualifications when using the cost values elsewhere.

### Communication formulas

The values below describe the logical payload convention used by the archived analysis script. They are not the compressed sizes of the checkpoint ZIP files.

| Symbol | Meaning | Value |
|---|---|---:|
| S | Full classifier state, bytes | 1,596,832 |
| B | FedNH body state, bytes | 1,579,288 |
| V | One 128-dimensional FP32 prototype, bytes | 512 |
| C | Number of classes | 34 |
| M | Reference samples | 680 |
| J | MP-FedCL prototypes per supported class | 3 |
| K | Number of clients | 10 or 100 |
| c_mean | Mean supported classes per client in the original partitions | 17.1 / 14.84 |

| Method | Upload bytes per client | Download bytes per client |
|---|---|---|
| FedAvg / FedALA | S | S |
| FedNH, 10C | B + V × c_mean | B + V × C |
| FedNH, 100C | B + V × C | B + V × C |
| FedPLVM | S + V × mean local prototype count | S + V × global prototype count |
| MP-FedCL | S + V × J × c_mean | S + V × C × K × J |
| CARD-FD | S + 4C + 4MC | S + 4MC + C + M |

At round 20, FedPLVM has total local/global prototype counts of 657/126 for 10C and 6,147/138 for 100C. Divide the local total by K to obtain the per-client mean. MP-FedCL sends the full padded global pool to each recipient; its download must not be divided by K again.

The model states include FP32 parameters and floating-point BatchNorm buffers plus INT64 counters. CARD-FD mask values use one byte per element in this accounting. The calculation excludes fixed sample/class-count metadata, dictionary keys, shape descriptors, serialization/transport overhead, optimizer states, checkpoint storage, and initialization traffic.

For Table 2, first obtain the per-client value within each configuration, then take the arithmetic mean of the two configurations where specified. MP-FedCL download remains a pair. Round only the final displayed values, to three decimal places.

## Manuscript and workflow

`Full-Source/Paper/Submitted/CARD-FD.pdf` is the archived submitted PDF supplied for this handover. `Overleaf.zip` contains the accompanying LaTeX project and figure assets, with `main.tex` at the archive root.

Preserve the submitted PDF as the record of the submission. If rebuilding or revising the LaTeX source, save the new PDF separately and compare it before labeling it as the submitted version. The presence of the source archive alone does not establish that a fresh compilation is byte-identical to the archived PDF.

To inspect or edit the manuscript, download and extract `Overleaf.zip`; its main document is `main.tex` at the archive root. Preserve the existing class, bibliography style, and figure assets. Do not replace the submitted PDF with a new compilation without checking the changes.

The analysis archive contains editable `inputs/CARD_FD_Workflow.drawio` and the exported workflow PNG. Open the `.drawio` file in diagrams.net to edit it, then export the required image. The workflow is a conceptual diagram; it is not generated from a numerical measurement table.

## Upload and verify the Drive handover

This section is for the maintainers preparing the research release.

1. Sign in to the Google account with upload permission and open the [designated Full Source folder](https://drive.google.com/drive/folders/1JpQNZV5AaicAjldENgG5P9i1FC5ZVVHo?usp=sharing).
2. Confirm sufficient storage. For an ordinary shared folder, uploads can count against the uploader's storage even when another person owns the folder; do not assume the mentor's account provides the quota. See [Google's upload documentation](https://support.google.com/drive/answer/2424368?hl=en).
3. Choose **New → Folder upload** and select the local `CARD-FD-Handover` directory. Keep `README.md` alongside its `Full-Source` subdirectory.
4. Alternatively, create the wrapper and `Full-Source` folder on Drive, upload the README, then upload `Analysis`, `Paper`, `Data`, and `Experiment` in batches. Upload each experiment method separately if easier to track. Choose one approach to avoid duplicate copies.
5. Keep the computer powered, connected, and awake until transfers complete. Retry individual failed items after checking their destination.
6. Check that all six methods have 10C/100C resources, both data archives are present, and all five CARD-FD 100C checkpoint archives are present.
7. Compare file counts and sizes. For important data/checkpoint archives, compare SHA-256 hashes between the original and a downloaded copy. Open representative downloaded archives and verify extraction.
8. Test the link with the intended recipient's account and ask the mentor to confirm access.

Existing ZIP files can be uploaded as they are. There is no need to recompress the entire handover into one large ZIP. If capacity is insufficient, agree on additional storage before omitting archived data or checkpoints.

## Upload this index to GitHub

This section applies to the documentation-only `CARD-FD-GitHub-Upload` directory, not the full dataset/checkpoint handover.

1. If using `CARD-FD-GitHub-Upload.zip`, extract it first.
2. Open [CARD-FD-Public](https://github.com/huuquyen2606/CARD-FD-Public) and sign in with an account authorized to contribute.
3. Select **Add file → Upload files**.
4. Drag the **contents inside** `CARD-FD-GitHub-Upload` into the upload area: `README.md`, `LICENSE`, `.gitignore`, `docs`, and `Full-Source`.
5. Ensure `README.md` appears at the repository root, not inside an extra `CARD-FD-GitHub-Upload` directory.
6. Confirm that the selected files are README.md, the existing license, .gitignore, and empty .gitkeep placeholders only. Do not upload the large handover or the ZIP as a single repository file.
7. Use a descriptive commit message, for example `Consolidate CARD-FD resource and reproduction guide`.
8. If appropriate for the team, create a new branch and a pull request for the mentor to review before merging. If you lack write access, request collaborator access or use the team's contribution process.
9. Open the rendered README, test its section links, and test the Drive link with the intended audience's permissions.

See [GitHub's file upload instructions](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository).

The included `.gitignore` allows this README, the license, and .gitkeep placeholders while excluding payload files when using Git. It does **not** filter files you manually select for browser upload. The existing Apache license is preserved. The empty .gitkeep files preserve the directory structure because Git does not preserve empty directories. Include these files when uploading folders; they contain no research data or instructions.

## Troubleshooting

| Symptom | What to check |
|---|---|
| GitHub download contains only documentation and .gitkeep files | Expected for this index. Download the actual resources from Drive. |
| Drive requests permission | Sign in with the intended account or request access from the folder owner. |
| Upload stops because storage is full | Check the uploader's quota and agree on storage before retrying large files. |
| A notebook cannot find a client CSV | Point `DATA_DIR`/`DATA_ROOT` to the extracted client/test directory, not the ZIP or its parent wrapper. The 100C export has a nested run directory. |
| A notebook immediately attempts to resume | Inspect `RESUME_CHECKPOINT`, `RESUME_FROM`, or `CHECKPOINT_INPUT_DIR`; use the selected notebook's documented fresh-run setting if needed. |
| Checkpoint restoration fails | Match method, configuration, architecture, feature/label order, preprocessing state, and required resume state. Do not substitute a different method's checkpoint. |
| `reproduce.py` is not found | Enter the analysis archive's internal `Full-Source/analysis` directory. Scripts are not included directly in this public index. |
| Analysis reports a missing Python package | Install requirements using the same interpreter used to launch the script, preferably the dedicated virtual environment. |
| `verify_submission.py` cannot find the PDF | Keep the extracted sibling `Full-Source/paper/submitted` directory and its reference PDF. |
| A workbook disagrees with the submitted FedAvg values | Use the verified PyTorch review records in the analysis package; historical workbook rows may predate the update. |
| Logs or metadata are overwritten while extracting CARD-FD 100C | Extract each session ZIP into a different destination. Their internal run paths overlap. |
| A generated PDF has a different checksum | PDF metadata or rendering-library versions may differ. Check numerical validation and rendering separately. |

## Verification and retention

The analysis package was executed from a fresh extraction and a different working directory. Its checks matched **84 numerical cells in Table 1** and **13 displayed values in Table 2** to the supplied submission PDF. The workflow matched the embedded image; the regenerated statistical and learning-curve figures matched the archived figure rendering in the checked environment.

These checks concern saved evidence, arithmetic, and rendering. They do not assert a new training/inference run, successful restoration of every checkpoint, or a complete integrity check of all multi-gigabyte archives. Environment versions for analysis are recorded in the analysis package; training environments must be checked separately.

Before removing local resources:

- Verify completed transfers, archive integrity, and recipient access.
- Keep independent backups for unique partition exports, checkpoints, and experimental records. The documentation-only GitHub repository is not a backup of those files.
- Retain the submitted PDF, notebook/configuration provenance, and resource links.
- Check whether a local directory is synchronized with Drive; deletion in a synchronized folder may propagate to the cloud.

## File inventory

The filenames below were inspected in the local handover. They identify expected Drive resources, not files embedded in this documentation repository. Remote upload completion is checked separately.

### Full-Source/Analysis

- `CARD_FD_analysis_handover.zip`
- `Statistic.zip`

### Full-Source/Data/100C

- `Raw_100C.zip`
- `data_preprocessing_100C.ipynb`
- `data_preprocessing_100C_logs.log`

### Full-Source/Data/10C

- `Raw_10C.zip`
- `Review_data_10C.zip`
- `data-preprocessing_10C.ipynb`
- `data-preprocessing_10C_logs.log`

### Full-Source/Experiment/CARD-FD/100C

- `CARD-FD_100C.ipynb`
- `CARD-FD_100C_checkpoint_R1.zip`
- `CARD-FD_100C_checkpoint_R12_R16.zip`
- `CARD-FD_100C_checkpoint_R17_R20.zip`
- `CARD-FD_100C_checkpoint_R2_R6.zip`
- `CARD-FD_100C_checkpoint_R7-R11.zip`
- `CARD-FD_100C_log_R1.log`
- `CARD-FD_100C_log_R12_R16.log`
- `CARD-FD_100C_log_R17_R20.log`
- `CARD-FD_100C_log_R2_R6.log`
- `CARD-FD_100C_log_R7_R11.log`

### Full-Source/Experiment/CARD-FD/10C

- `CARD-FD_10C.ipynb`
- `CARD-FD_10C_checkpoint.zip`
- `CARD-FD_10C_log_R11_R20.log`
- `CARD-FD_10C_log_R1_R10.log`

### Full-Source/Experiment/FedALA/100C

- `FedALA_100C.ipynb`
- `FedALA_100C_checkpoint.zip`
- `FedALA_100C_logs_R9_R20.log`
- `FedALA_100C_logs__R1_R8.log`

### Full-Source/Experiment/FedALA/10C

- `FedALA_10C.ipynb`
- `FedALA_10C__log_R6_R15.log`
- `FedALA_10C_checkpoint.zip`
- `FedALA_10C_log_R16_R35.log`
- `FedALA_10C_log_R1_R5.log`

### Full-Source/Experiment/FedAvg/100C

- `FedAvg_100C.ipynb`
- `FedAvg_100C_checkpoint.zip`
- `FedAvg_100C_logs.log`

### Full-Source/Experiment/FedAvg/10C

- `FedAvg_10C.ipynb`
- `FedAvg_10C_checkpoint.zip`
- `FedAvg_10C_log.log`

### Full-Source/Experiment/FedNH/100C

- `FedNH_100C.ipynb`
- `FedNH_100C_checkpoint.zip`
- `FedNH_100C_logs.log`

### Full-Source/Experiment/FedNH/10C

- `FedNH_10C.ipynb`
- `FedNH_10C_checkpoint.zip`
- `FedNH_10C_logs.log`

### Full-Source/Experiment/FedPLVM/100C

- `FedPLVM_100C.ipynb`
- `FedPLVM_100C_checkpoint.zip`
- `FedPLVM_100C_logs_R1_R2.log`
- `FedPLVM_100C_logs_R3_R20.log`

### Full-Source/Experiment/FedPLVM/10C

- `FedPLVM_10C.ipynb`
- `FedPLVM_10C_checkpoint.zip`
- `FedPLVM_10C_logs_R1_R5.log`
- `FedPLVM_10C_logs_R6_R40.log`

### Full-Source/Experiment/MP-FedCL/100C

- `MP-FedCL_100C.ipynb`
- `MP-FedCL_100C_checkpoint.zip`
- `MP-FedCL_100C_logs.log`

### Full-Source/Experiment/MP-FedCL/10C

- `MP-FedCL_10C.ipynb`
- `MP-FedCL_10C_checkpoint.zip`
- `MP-FedCL_10C_logs_R6-R30.log`
- `MP-FedCL_logs_R1_R5.log`

### Full-Source/Paper/Submitted

- `CARD-FD.pdf`
- `Overleaf.zip`

## Publication and license

The manuscript is submitted to SOICT 2026. This guide does not assert acceptance, proceedings publication, or a paper DOI. Consult the submitted manuscript for its title, author list, and reported results.

The repository retains the existing [Apache License 2.0](LICENSE). Consult the notices accompanying third-party datasets and dependencies for their applicable terms.
