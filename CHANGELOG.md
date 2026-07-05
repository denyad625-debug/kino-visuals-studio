# Changelog

All notable changes to the KINO Visuals Studio project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [3.0.0] — 2026-07-04

### Added
- **8 Specialized AI Experts**: Lighting, Material, Motion, Lens, Post-Processing, Structure, Golden (ground truth), and Quality evaluation experts
- **Intelligent Spiral Learning (ISL)**: Progressive multi-cycle training methodology with 5 cycles (20% → 40% → 60% → 80% → 100%)
- **Knowledge Fusion**: Three merge strategies — average, weighted, and best-pick for combining expertise from multiple reference videos
- **Deep Q-Network (DQN) Agents**: Reinforcement learning agents for all 7 expert domains with experience replay and proxy models
- **Federated Swarm Supervision**: Distributed quality monitoring across training environments with SSIM/MSE validation
- **Web Dashboard**: Real-time training monitoring, style management, and system control via Flask web interface
- **REST API Gateway**: Programmatic access for n8n workflow automation and external integrations
- **Professional CSS Framework**: 50+ design variables, 25 sections, 3 breakpoints, RTL support, animations

### Changed
- **Architecture Migration**: Transitioned from monolithic pipeline to modular expert swarm architecture
- **Training Pipeline**: Replaced single-pass training with multi-cycle spiral learning
- **Style Management**: Centralized style operations through StyleManager with unified API

### Fixed
- Camera intrinsics handling in pose estimation bridge
- Cross-environment geometry transfer via USR Bundle format
- Point cloud processing with configurable limits and normal estimation

---

## [2.1.0] — 2026-06-29

### Added
- **USR Bundle Format**: Universal Scene Representation for cross-environment geometry transfer
- **Geometry Intelligence Layer**: Automated provider selection, health monitoring, and benchmark-driven optimization
- **Geometry Engine**: Central orchestrator with caching, fusion strategies, and versioning
- **Multi-View Stereo Provider**: RGB frame to depth map reconstruction
- **P22 Architecture Freeze**: Canonical architecture review and design freeze

### Changed
- Geometry pipeline refactored into three-layer architecture (Provider → Engine → Intelligence)
- Cache system extended with mesh serialization and bundle save/load capabilities

---

## [2.0.0] — 2026-06-20

### Added
- **Geometry Provider Layer**: Abstract base class with multi-view stereo and file provider implementations
- **Point Cloud Processing**: Poisson surface reconstruction, ball-pivot, and alpha shape methods
- **DeepMesh Integration**: Open3D-based mesh reconstruction from depth maps and point clouds
- **Cross-Environment Bridge**: Subprocess-based communication between cu128 (conda) and Point2Mesh (venv) environments
- **Benchmark Suite**: Geometry engine benchmarking with configurable parameters

### Changed
- Mesh reconstruction pipeline separated into dedicated Environment B (Point2Mesh venv)
- Point cloud fusion moved from provider to engine layer

---

## [1.1.0] — 2026-06-10

### Added
- **Camera Pose Estimation**: 6-DoF camera pose computation, depth map generation, and intrinsics extraction from reference video
- **Golden Expert**: Ground truth data extraction and quality reference for training
- **Quality Expert**: Automated style quality evaluation against golden data
- **Imitation Expert**: Behavioral cloning from reference video analysis
- **Training Curriculum**: Multi-stage progressive training with increasing complexity

### Changed
- Expert training enhanced with camera pose data (camera poses, depth maps, intrinsics)
- Style metadata extended with camera pose usage tracking

---

## [1.0.0] — 2026-05-28

### Added
- **Initial Production Release**
- **6 Core AI Experts**: Lighting, Material, Motion, Lens, Post-Processing, Structure
- **StyleManager**: Centralized style training and management system
- **KinoAssembler**: Full pipeline orchestration from scene setup to final render
- **KinoCentralBrain**: DNA data unification and master settings management
- **Blender Integration**: Automated scene assembly, material application, and Cycles rendering
- **Unreal Engine 5.7 Automation**: Nanite mesh support, Substrate materials, Lumen HW RT, DLSS 3.0
- **Progress Tracker**: Real-time rendering progress monitoring with HTML reports
- **Configuration System**: Centralized `kino_config.json` with environment variable overrides
- **Quality Presets**: Draft, HD, Full HD, Cinematic, and 4K render configurations

---

## [0.7.0] — 2026-05-15

### Added
- **Base Agent Framework**: Abstract base class for all AI experts with standardized interfaces
- **Initial Expert Prototypes**: Lighting, Material, and Motion experts with basic training loops
- **Video Analysis Pipeline**: Frame extraction, temporal DNA analysis, and keyframe detection
- **Blender Scripting**: Basic scene manipulation and rendering automation
- **Project Structure**: Modular codebase organization with experts/, spiral_learning/, and data/ directories

### Changed
- Migrated from monolithic scripts to modular agent-based architecture

---

## [0.5.0] — 2026-05-01

### Added
- **Initial Prototype**: Proof-of-concept video analysis and style transfer
- **Basic Training Loop**: Single-expert training on reference video
- **Q-Learning Foundation**: Tabular Q-learning for visual style parameters
- **Experimental Framework**: Ablation studies and cross-dataset generalization testing

---

## [0.1.0] — 2026-04-15

### Added
- **Project Inception**: Initial repository setup and concept validation
- **Research Phase**: Feasibility studies for AI-driven visual style transfer
- **Technology Stack Selection**: Python, Blender, PyTorch, Open3D
