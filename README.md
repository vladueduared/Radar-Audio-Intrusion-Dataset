
# Radar-Audio Intrusion Dataset for Privacy-Preserving Indoor Alarm Detection

This repository contains a multimodal radar-audio dataset collected for camera-free indoor intrusion-related alarm detection.

The dataset combines 60 GHz radar macro-detection data and stereo audio recordings acquired in indoor environments using Infineon CY8CKIT-062S2-AI sensing platforms.

The dataset was developed to support the study:

**Limited-Data Radar–Audio Fusion for Small-Room Indoor Intrusion Detection: Window-Level and Stateful Alarm Evaluation**

## Dataset Overview

The complete dataset contains 80 recording sessions acquired in two indoor environments.

| Environment | Sessions | Role |
|---|---:|---|
| Room 1 | S001-S070 | Model development and primary evaluation |
| Room 2 | S071-S080 | External cross-environment evaluation |

Room 1 was used for dataset construction, model development, validation, threshold selection, and primary testing.

Room 2 was located in a different building and had a comparable room size and sensing configuration, while differing in wall construction, flooring, door, window, furniture, and other environmental characteristics.

Room 2 was used exclusively for external evaluation. No Room 2 data were used for model training, feature-scaling estimation, classifier selection, decision-threshold selection, fusion-rule selection, or stateful alarm parameter tuning.

## Repository Structure

```text
radar-audio-intrusion-dataset/
│
├── README.md
├── ETHICS.md
├── LABELS.md
├── CITATION.cff
├── sessions.csv
│
├── room1_development/
│   ├── S001_...
│   ├── S002_...
│   ├── ...
│   └── S070_...
│
└── room2_external_evaluation/
    ├── sessions_room2.xlsx
    ├── S071_positive_door_entry_handle_impact/
    ├── S072_positive_door_entry_speech/
    ├── S073_positive_door_entry_stealth/
    ├── S074_positive_door_entry_slow_fast/
    ├── S075_negative_falling_object_door_knock/
    ├── S076_positive_door_entry_fast/
    ├── S077_negative_ambient_noise_speech/
    ├── S078_positive_door_entry_thrown_object_door_knock/
    ├── S079_positive_window_entry/
    └── S080_positive_window_entry_door_opening/
