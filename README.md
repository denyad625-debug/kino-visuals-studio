# KINO Visuals Studio

<p align="center">
  <img src="assets/logo/logo.svg" alt="KINO Visuals Studio" width="400"/>
</p>

<p align="center">
  <em>AI-Powered Cinematic Visual Intelligence Platform</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python" alt="Python 3.12"/>
  <img src="https://img.shields.io/badge/Blender-4.2-orange?style=for-the-badge&logo=blender" alt="Blender 4.2"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="MIT License"/>
  <img src="https://img.shields.io/badge/Status-Production--Ready-brightgreen?style=for-the-badge" alt="Production Ready"/>
  <img src="https://img.shields.io/badge/CUDA-12.8-76B900?style=for-the-badge&logo=nvidia" alt="CUDA 12.8"/>
  <img src="https://img.shields.io/badge/PyTorch-2.0-EE4C2C?style=for-the-badge&logo=pytorch" alt="PyTorch 2.0"/>
</p>

---

## Overview

KINO Visuals Studio is an end-to-end AI pipeline that analyzes reference video footage, extracts cinematic visual DNA, and trains a swarm of specialized AI experts to reproduce those visual patterns on 3D scenes. The system uses **Intelligent Spiral Learning (ISL)** — a progressive, multi-cycle training methodology — to achieve professional-grade cinematic output.

The platform bridges computer vision, reinforcement learning, and 3D rendering into a unified production pipeline, enabling automated visual style transfer from reference video to 3D scene.

---

## Features

### AI Pipeline

- **8 Specialized AI Experts** — Lighting, Material, Motion, Lens, Post-Processing, Structure, Golden (ground truth), and Quality (evaluation)
- **Intelligent Spiral Learning (ISL)** — Progressive multi-cycle training (20% → 100%) with cumulative knowledge building
- **Knowledge Fusion** — Merge expertise from multiple reference videos using average, weighted, or best-pick strategies
- **Deep Q-Network (DQN)** — Reinforcement learning agents for autonomous visual decision-making
- **Federated Swarm Supervision** — Distributed quality monitoring across training environments

### Geometry Pipeline

- **Multi-View Stereo** — 3D reconstruction from RGB frames via geometry provider
- **Point Cloud Processing** — Poisson surface reconstruction, statistical outlier removal, normal estimation
- **USR Bundle Format** — Universal Scene Representation for cross-environment geometry transfer
- **Geometry Intelligence** — Automated provider selection, health monitoring, and benchmark-driven optimization

### Rendering & Integration

- **Blender Integration** — Automated scene assembly, material application, lighting, camera motion, and rendering
- **Unreal Engine 5.7** — Nanite mesh support, Substrate materials, Lumen Hardware RT, DLSS 3.0
- **Web Dashboard** — Real-time training monitoring, style management, and system control
- **REST API & n8n Gateway** — Programmatic access and workflow automation

### Video Analysis

- **Temporal DNA Extraction** — Per-frame analysis of motion, lighting, color, and composition
- **Camera Pose Estimation** — 6-DoF camera tracking from reference video
- **Depth Map Generation** — Per-frame depth estimation for 3D reconstruction
- **Keyframe Detection** — Automatic identification of important frames

---

## Architecture

```text
┌─────────────────────────────────────────────────────────────────┐
│                        INPUT LAYER                               │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌────────────────┐  │
│  │ RGB      │  │ Camera   │  │ Depth    │  │ Segmentation   │  │
│  │ Frames   │  │ Poses    │  │ Maps     │  │ Masks          │  │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └───────┬────────┘  │
└───────┼──────────────┼──────────────┼────────────────┼──────────┘
        │              │              │                │
┌───────▼──────────────▼──────────────▼────────────────▼──────────┐
│                      AI EXPERTS LAYER                            │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────────────────┐  │
│  │ Lighting │ │ Material │ │  Motion  │ │  Lens Specialist   │  │
│  │  Expert  │ │  Expert  │ │  Expert  │ │  (Camera Intrins.) │  │
│  └──────────┘ └──────────┘ └──────────┘ └────────────────────┘  │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────────────────┐  │
│  │  Post    │ │Structure │ │  Golden  │ │     Quality        │  │
│  │Processing│ │  Expert  │ │  Expert  │ │     Expert         │  │
│  └──────────┘ └──────────┘ └──────────┘ └────────────────────┘  │
└──────────────────────────────────────────────────────────────────┘
        │
┌───────▼──────────────────────────────────────────────────────────┐
│                    ORCHESTRATION LAYER                            │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐   │
│  │ StyleManager │  │ KinoAssembler│  │  KinoCentralBrain    │   │
│  │ (Training)   │  │ (Pipeline)   │  │  (DNA Unification)   │   │
│  └──────────────┘  └──────────────┘  └──────────────────────┘   │
└──────────────────────────────────────────────────────────────────┘
        │
┌───────▼──────────────────────────────────────────────────────────┐
│                    GEOMETRY LAYER                                 │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐   │
│  │Geometry      │  │ Geometry     │  │  Geometry            │   │
│  │Provider      │  │ Engine       │  │  Intelligence        │   │
│  │(RGB→Depth)   │  │ (Cache/Fuse) │  │  (Selector/Monitor)  │   │
│  └──────────────┘  └──────────────┘  └──────────────────────┘   │
└──────────────────────────────────────────────────────────────────┘
        │
┌───────▼──────────────────────────────────────────────────────────┐
│                    RENDERING LAYER                                │
│  ┌──────────────┐  ┌──────────────────┐  ┌──────────────────┐   │
│  │ Blender      │  │  Unreal Engine   │  │  Web Dashboard   │   │
│  │ (Cycles)     │  │  5.7 (Nanite)    │  │  (Flask)         │   │
│  └──────────────┘  └──────────────────┘  └──────────────────┘   │
└──────────────────────────────────────────────────────────────────┘
```

---

## Pipeline

### Training Flow

1. **Reference Video Input** — Upload reference footage for style analysis
2. **Frame Extraction** — Extract RGB frames at configurable sample rate
3. **Camera Pose Estimation** — Compute 6-DoF camera poses per frame
4. **Depth Map Generation** — Generate per-frame depth maps
5. **Expert Training** — Each AI expert trains independently using DQN reinforcement learning
6. **Spiral Learning** — Progressive multi-cycle refinement (5 cycles: 20% → 100%)
7. **Knowledge Fusion** — Merge expertise from multiple reference videos
8. **Quality Evaluation** — Assess output quality against golden data

### Inference Flow

1. **Scene Setup** — Load 3D scene in Blender
2. **Expert Application** — Each expert applies learned style to the scene
3. **Pipeline Assembly** — KinoAssembler orchestrates the full pipeline
4. **Rendering** — Cycles render engine with configurable quality presets
5. **Post-Processing** — Color grading, effects, and final output

---

## Documentation

| Document | Description |
|----------|-------------|
| [`docs/Architecture.pdf`](docs/Architecture.pdf) | High-level system architecture overview |
| [`docs/System_Requirements.pdf`](docs/System_Requirements.pdf) | Hardware and software requirements |
| [`docs/Roadmap.pdf`](docs/Roadmap.pdf) | Development roadmap and milestones |
| [`CHANGELOG.md`](CHANGELOG.md) | Version history and milestones |

---

## Getting Started

### Prerequisites

| Component | Version | Purpose |
|-----------|---------|---------|
| Python | 3.12+ | Runtime environment |
| Blender | 4.2+ | 3D rendering engine |
| CUDA | 12.8 | GPU acceleration |
| Git | Latest | Version control |

### Installation

```bash
# Clone the repository
git clone https://github.com/denyad625-debug/kino-visuals-studio.git
cd kino-visuals-studio

# Install core dependencies
pip install -r requirements.txt

# (Optional) Install PyTorch with CUDA support
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu118
```

### Quick Start

```python
from style_manager import StyleManager

manager = StyleManager()

# Train all 8 experts on a reference video
results = manager.train_all(
    video_path="reference.mp4",
    style_name="cinematic_style",
    episodes=100
)

# View trained styles
manager.show_styles()
```

---

## System Requirements

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| **OS** | Linux (Ubuntu 22.04+) | Linux (Ubuntu 24.04+) |
| **Python** | 3.12 | 3.12 |
| **CUDA** | 12.4 | 12.8 |
| **GPU** | NVIDIA RTX 3060 (12 GB) | NVIDIA RTX 4090 (24 GB) |
| **RAM** | 32 GB | 64 GB |
| **Storage** | 50 GB SSD | 200 GB NVMe SSD |
| **Blender** | 4.2 | 4.2+ |
| **Unreal Engine** | 5.7 (optional) | 5.7 |

See [`docs/System_Requirements.pdf`](docs/System_Requirements.pdf) for full details.

---

## Development Status

| Component | Status |
|-----------|--------|
| Core AI Experts (8) | ✅ Production-ready |
| Intelligent Spiral Learning | ✅ Production-ready |
| DQN Training Pipeline | ✅ Production-ready |
| Geometry Provider (RGB → Depth) | ✅ Production-ready |
| Geometry Engine & Cache | ✅ Production-ready |
| Geometry Intelligence | ✅ Production-ready |
| USR Bundle Format | ✅ Complete |
| Blender Integration | ✅ Production-ready |
| Web Dashboard | ✅ Production-ready |
| REST API Gateway | ✅ Production-ready |
| Unreal Engine 5.7 Automation | ✅ Complete |
| Geometry Fusion Strategies | 🔧 Design complete |
| Texture/UV Pipeline | 📋 Planned |
| Neural Reconstruction | 📋 Future |

---

## License

This project is licensed under the MIT License — see the [`LICENSE`](LICENSE) file for details.

---

<p align="center">
  <sub>Built with Python, Blender, PyTorch, and Open3D</sub>
</p>
