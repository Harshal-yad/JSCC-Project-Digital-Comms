# 6G JSCC: Bandwidth-Optimized Dual-Mode Architecture

A reproducible research-style demonstration of a dual-mode semantic communication system for 6G-style wireless image transmission. This project compares:

- Human mode: transmits a compressed latent representation for image reconstruction.
- Machine mode: transmits a compact semantic feature vector for downstream classification.

The notebook explores how the system behaves under additive white Gaussian noise (AWGN), compares human and machine performance, and visualizes the trade-off between reconstruction fidelity and communication bandwidth.

## Why this project matters

In future wireless networks, not all traffic is meant for human consumption. Some content will be interpreted by machines, while other data must still be reconstructed visually. This repository illustrates a simple but useful idea:

- keep a low-bandwidth semantic representation for machine tasks,
- keep a richer latent representation for human-centered reconstruction,
- evaluate both under realistic channel conditions.

It is designed as a compact educational and research demonstration rather than a production telecom stack.

## Repository structure

```text
JSCC-Project-Digital-Comms/
├── README.md
├── 6g_jscc_dual_architecture_demo.ipynb
├── traffic_data/                     # expected local dataset folder
└── results/
    └── figures/
        ├── figure1_qualitative_human_reconstructions.png
        ├── figure2_performance_vs_snr.png
        ├── figure3_jscc_vs_digital_cliff_effect.png
        └── figure4_bandwidth_comparison.pdf
```

## What is implemented

The notebook contains a full demonstration of:

- dataset loading for a two-class traffic image dataset,
- VAE-based latent compression for the human mode,
- compact 128-D semantic encoder for the machine mode,
- AWGN channel simulation across SNR values,
- performance evaluation for reconstruction quality and classification accuracy,
- bandwidth comparison against raw image transmission,
- publication-style figure generation.

## Core concept

### Human mode

The human branch uses a frozen Stable Diffusion VAE to encode images into a latent space. This representation is transmitted over an AWGN channel and then decoded to reconstruct the image.

### Machine mode

The machine branch uses a lightweight encoder to produce a 128-dimensional feature vector. The classifier receives this vector under noisy channel conditions and predicts the traffic class.

### Observed trade-off

The notebook explicitly illustrates the common semantic communication trade-off:

- human mode preserves visual fidelity with higher payload size,
- machine mode offers dramatically smaller payload and strong task performance,
- both degrade as SNR decreases, with the digital baseline showing a harsh cliff effect.

## Expected setup

This project expects a local dataset folder named `traffic_data` in the repository root. The notebook uses `ImageFolder` structure with class directories such as:

```text
traffic_data/
├── highway/
│   ├── image_001.png
│   └── ...
└── urban/
    ├── image_001.png
    └── ...
```

## Requirements

Python 3.10+ is recommended.

Install the main dependencies with:

```bash
pip install torch torchvision diffusers matplotlib seaborn scikit-learn numpy
```

If you are using a GPU, ensure your CUDA-enabled PyTorch build is installed.

## Quick start

1. Clone the repository.
2. Place your dataset in `./traffic_data`.
3. Open `6g_jscc_dual_architecture_demo.ipynb` in Jupyter or VS Code.
4. Run the notebook cells in order.
5. Generated figures will be saved under `results/figures/`.

## Generated outputs

The notebook creates publication-style plots for:

- qualitative image reconstructions in human mode,
- performance vs. SNR for reconstruction and classification,
- comparison with a digital cliff effect baseline,
- bandwidth savings relative to raw RGB transmission.

## Research note

This repository is a compact demonstration and educational reference. It is not intended to be a standards-compliant modem, source codec, or full end-to-end wireless communication simulator. The implementation is designed to be easy to read, reproducible, and visually interpretable.

## License

This repository does not currently declare a license file. If you plan to reuse or distribute it, verify whether a license is intended before publishing or extending the work.

## Acknowledgments

This work builds on the ideas of joint source-channel coding and semantic communication, using a VAE-based encoder and a compact task-oriented transmission pipeline for a simple image classification scenario.

## Contributing

Pull requests and improvements are welcome. If you extend the model, improve the plots, or add a cleaner dataset pipeline, please open a contribution with a clear description of the change.
