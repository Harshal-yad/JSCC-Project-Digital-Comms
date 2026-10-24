# JSCC Project: Digital Communications

This repository contains a research-oriented notebook and supporting materials for a 6G joint source-channel coding (JSCC) and semantic communication study. The project explores a dual-mode communication pipeline where the system transmits either:

- a human-oriented latent representation for image reconstruction, or
- a machine-oriented semantic representation for downstream task execution.

The work is designed to illustrate the trade-off between reconstruction fidelity and task efficiency under noisy wireless communication channels.

## Project overview

The main notebook, `JSCC_6g.ipynb`, is a reproducible demonstration of a dual-mode semantic communication system for 6G-style digital communications. It focuses on:

- transmitting compressed representations over a noisy channel,
- comparing human and machine communication modes,
- evaluating performance under varying signal-to-noise ratios (SNR),
- analyzing the effectiveness of semantic communication versus traditional digital transmission.

The repository also includes the written report, presentation slides, poster, and generated result artifacts used for the project.

## Repository structure

```text
JSCC-Project-Digital-Comms/
├── README.md
├── JSCC_6g.ipynb                        # main project notebook
├── poster/
│   └── 6G_JSCC_A3_Poster.pptx
|   └── 6G_JSCC_A3_Poster.pdf
├── presentation/
│   └── 6G_JSCC_Project_Presentation.pptx
|   └── 6G_JSCC_Project_Presentation.pdf
├── report/
│   └── Task_Aware_Dynamic_Semantic_Compression_Mini_Project_Report.docx
|   └── Task_Aware_Dynamic_Semantic_Compression_Mini_Project_Report.pdf
├── results/
│   ├── figures/
└── (optional local dataset folder)
```

## What the notebook covers

The notebook demonstrates several core ideas in semantic and wireless communication research:

- latent representation learning for image reconstruction,
- compact task-aware semantic encoding for machine inference,
- AWGN channel simulation,
- performance analysis across multiple SNR values,
- comparison between semantic transmission and conventional digital communication,
- visual and quantitative evaluation of system behavior.

## Human vs machine mode

### Human mode

This mode prioritizes perceptual fidelity and reconstructs the original image from a compressed latent representation.

### Machine mode

This mode prioritizes task utility by compressing the input into a lightweight semantic embedding that can be used for classification or inference.

This dual-mode setup highlights the central idea behind semantic communications: a representation optimized for the communication goal may be more efficient than transmitting raw data directly.

## Requirements

The project is implemented in Python and is intended for Jupyter Notebook-based execution.

Recommended environment:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install torch torchvision torchaudio numpy matplotlib seaborn scikit-learn diffusers jupyter
```

Depending on the notebook implementation and model dependencies, additional libraries may be required. If you are using a GPU, install a CUDA-enabled PyTorch build for better performance.

## Getting started

1. Clone the repository:

```bash
git clone https://github.com/Harshal-yad/JSCC-Project-Digital-Comms.git
cd JSCC-Project-Digital-Comms
```

2. Open the notebook in Jupyter or VS Code:

```bash
jupyter notebook JSCC_6g.ipynb
```

3. Run the notebook cells in order.

4. Review generated outputs in the `results/` folder.

## Output artifacts

The project includes:

- a report in `report/`
- presentation slides in `presentation/`
- a poster in `poster/`
- figure and metric outputs under `results/`

These materials are useful for both understanding the methodology and presenting the project in academic or research-oriented settings.

## Notes

- This repository is primarily a research/demo project rather than a production communication library.
- Some experiments may depend on a local dataset or generated assets that are not included in the GitHub repository.
- The notebook is the main source of the implementation and experimentation flow.

## License

This repository does not currently include an explicit license file. If you plan to reuse, publish, or extend the project, confirm whether a license is intended before distributing it publicly.

## Acknowledgments

This project builds on concepts from joint source-channel coding, semantic communication, and 6G wireless system design. It is intended as a compact educational and research demonstration of how communication systems can be optimized for both human and machine-oriented tasks.
