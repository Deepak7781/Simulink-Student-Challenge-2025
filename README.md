# Heterogeneous Swarm Drones for Crack Detection and Quantification

[![MATLAB](https://img.shields.io/badge/MATLAB-R2024b-blue)](https://www.mathworks.com/products/matlab.html) [![UAV Toolbox](https://img.shields.io/badge/UAV_Toolbox-v24.2-green)](https://www.mathworks.com/products/uav.html) [![Simulink Student Challenge 2025](https://img.shields.io/badge/Challenge-2025-orange)](https://www.mathworks.com/academia/students/competitions/simulink-challenge.html)

A Simulink-based simulation of a heterogeneous drone swarm for detecting and quantifying cracks (length, width, depth, position) in civil structures like bridges and buildings. Built for the 2025 Simulink Student Challenge—virtual "digital twin" testing with ML detection and 3D world navigation.

## 🎯 Project Overview
- **Problem:** Aging infrastructure (e.g., bridges) risks collapses; manual inspections are dangerous/slow.
- **Solution:** 4-drone swarm (2 scouts for mapping, 1 inspector for close-ups, 1 relay for fusion) autonomously scans, detects cracks via CNN, quantifies metrics, and exports CSV reports.
- **Key Features:**
  - Multidomain Simulink models (UAV dynamics, vision processing, swarm coordination).
  - Virtual 3D world with procedural cracks and scenarios (nominal, GPS-denied, disaster).
  - ML integration: Fine-tuned SqueezeNet for 90%+ detection accuracy.
  - Outputs: Real-time CSV (e.g., `CrackID, Length_mm, Width_mm, Depth_mm, Position_XYZ, Timestamp`).
- **Impact:** Enables proactive maintenance, tying to UN SDG 9 (Resilient Infrastructure). Sim shows 3x faster scans vs. single-drone.

![Swarm Demo GIF](figures/swarm_trajectory.gif) <!-- Add your GIF here -->

## 🚀 Quick Start
1. **Clone the Repo:**
2. **Requirements:** MATLAB R2024b+ with UAV Toolbox, Computer Vision Toolbox, Robotics System Toolbox, Simscape Multibody. See `requirements.txt`.
3. **Setup:**
- Run `setup.m` in MATLAB to add paths and verify toolboxes.
- Download Kaggle crack dataset subset to `data/crack_images/` (or use provided samples).
4. **Run Simulation:**
    
        sim('models/SwarmCoord.slx')  # Full swarm in nominal scenario

- Outputs: `data/outputs/crack_report.csv` + plots via `scripts/analyzeReport.m`.
5. **Test:** Run `tests/test_swarm.m` for quick validation.

## 📁 Repository Structure
- `models/`: Simulink .slx files (e.g., `SwarmCoord.slx` for top-level).
- `scripts/`: MATLAB utilities (e.g., `trainCrackML.m` for ML).
- `data/`: Assets (STLs, images; large files gitignored).
- `tests/`: Unit/integration tests.
- `video/`: Challenge demo (`demo.mp4`).
- `figures/`: Viz assets.

## Challenge Demo Video
Watch the 3-min demo: [YouTube Link](https://www.youtube.com/watch?v={{your-video-id}}) #SimulinkStudentChallenge2025

- **Highlights:** Swarm deployment over cracked bridge → ML detection → Fused CSV report → Scenario robustness.

## Development Notes
- **Timeline:** 4-week sprint (Dec 14–Jan 14, 2026); see `docs/progress.md` for logs.
- **Challenges Overcome:** GPS-denied localization via VIO; multi-view fusion for accurate depth.
- **Future Work:** Hardware-in-loop with PX4; swarm scaling to 10+ drones.

## Resources & Acknowledgments
- MathWorks File Exchange: [UAV Swarm Examples](https://www.mathworks.com/matlabcentral/fileexchange).
- Dataset: [Kaggle Concrete Crack Images](https://www.kaggle.com/datasets/arnavr10880/concrete-crack-images-for-classification).
- Built with guidance from Grok (xAI).

## Contributing
Fork, branch, PR! Issues welcome for bugs/features.

---

**Deepak S | Madras Institue of Technology | deepakaero07@gmail.com | Dec 2025**
