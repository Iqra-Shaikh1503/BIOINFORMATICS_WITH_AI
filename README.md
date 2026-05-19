AI-Driven Drug Discovery Pipeline for Acetylcholinesterase
Overview

This project demonstrates a complete AI-driven drug discovery workflow targeting Human Acetylcholinesterase (AChE) using machine learning, bioinformatics, cheminformatics, and molecular docking techniques.

The pipeline was developed as part of a 7-day workshop project and integrates:

ChEMBL database mining
Molecular fingerprint generation using RDKit
Machine Learning classification with Random Forest
Activity prediction of new molecules
Protein-ligand docking using AutoDock Vina
3D molecular visualization using Py3Dmol

The project predicts whether compounds are active inhibitors of Acetylcholinesterase and validates predictions through molecular docking simulations.

Project Workflow
Day 1 — Dataset Collection
Fetched bioactivity data for Human Acetylcholinesterase (CHEMBL220) from the ChEMBL database.
Selected compounds with IC50 activity values.
Prepared and cleaned the dataset.
Activity Classification
Active → IC50 < 5000 nM
Inactive → IC50 ≥ 5000 nM
Day 2 — Feature Engineering

Generated Morgan Fingerprints (ECFP4) using RDKit.

Features
Radius: 2
Fingerprint Size: 1024 bits

These fingerprints convert molecular structures into machine-learning-readable vectors.

Day 3 — Machine Learning Model

Built a Random Forest Classifier using Scikit-learn.

Model Details
Algorithm: Random Forest
Train/Test Split: 80/20
Evaluation Metrics:
Accuracy Score
Confusion Matrix
Day 4 — Prediction on New Molecules

Tested the trained model on:

Donepezil (known AChE inhibitor)
Hexane (inactive control molecule)

The model predicts whether a molecule is:

ACTIVE 🟢
INACTIVE 🔴
Day 5 — Protein & Ligand Preparation

Downloaded protein structure:

PDB ID: 4EY7
Preparation Steps
Removed water molecules and native ligand
Converted receptor and ligand to PDBQT format
Generated 3D ligand conformations using OpenBabel
Day 6 — Molecular Docking

Performed molecular docking using AutoDock Vina.

Docking Parameters
Exhaustiveness: 8
Grid Size: 20 × 20 × 20
Active site center calculated automatically from native ligand coordinates
Visualization

Used Py3Dmol to render:

Protein structure
Docked ligand pose
Binding interactions
Day 7 — Interpretation
Machine learning identified promising inhibitors.
Docking validated binding affinity inside the active site.
Binding energy confirmed the predicted inhibitory potential.
Technologies Used
Programming Language
Python
Libraries & Tools
RDKit
Scikit-learn
Pandas
NumPy
BioPython
Py3Dmol
ChEMBL Web Resource Client
AutoDock Vina
OpenBabel





Project Structure
├── drug_discovery_pipeline.ipynb
├── receptor.pdb
├── receptor.pdbqt
├── ligand.pdbqt
├── result.pdbqt
├── result1.pdb
├── conf.txt
├── vina_log.txt
└── README.md
