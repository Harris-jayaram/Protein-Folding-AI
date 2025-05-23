AI Protein Folding Model with Graph Neural Networks and ESM-2 Embeddings

Overview
This project, developed as part of a B.Tech AI & Data Science curriculum, focuses on predicting protein structures and analyzing the effects of mutations using Graph Neural Networks (GNNs) and ESM-2 embeddings. Proteins are represented as graphs, where amino acid residues are nodes, and spatial proximity defines edges. The model integrates ESM-2 embeddings for enhanced biological feature representation and uses GNNs to predict 3D structures. Key features include mutation analysis (RMSD, energy differences, secondary structure changes), interactive visualizations, and Excel export for results.
This project was completed and documented on 09:43 PM IST on Friday, May 23, 2025.
Features

Protein Structure Prediction: Uses GNNs to predict 3D coordinates of protein residues.
ESM-2 Embeddings: Integrates esm2_t12_35M_UR50D embeddings for rich biological feature representation.
Mutation Analysis: Computes RMSD, energy differences, secondary structure changes, and confidence scores for mutations.
Interactive Visualizations: Generates Plotly-based HTML visualizations:
protein_comparison.html: Full-screen 3D comparison of original and mutated structures.
rmsd_comparison.html: Bar chart of RMSD values.
energy_rmsd_comparison.html: Dual-axis chart comparing RMSD and energy differences.
ss_changes.html: Grouped bar chart of secondary structure changes.


Excel Export: Saves results (RMSD, confidence, energy, secondary structure) to mutation_analysis.xlsx.

Prerequisites
This project is implemented in Google Colab. The following libraries are required:

torch==2.0.0
torch-geometric==2.0.4
biopython==1.79
numpy==1.23.0
pandas==1.5.0
plotly==5.10.0
scikit-learn==1.2.0
transformers
openpyxl

Download Dataset
To run this project, you’ll need protein structure data in PDB format. You can download datasets from the RCSB Protein Data Bank (PDB), which provides access to experimentally determined 3D structures of proteins.

RCSB PDB Download Link: Visit the RCSB PDB File Download Services to download PDB files. You can access coordinate files directly at https://files.rcsb.org/pub/pdb/data/structures/divided/pdb.
Batch Download: For downloading multiple PDB files, use the RCSB PDB Batch Download Service which provides a shell script for efficient batch downloads.
Example PDB Files: For testing, you can download small protein structures like 1ubq.pdb (ubiquitin) or 6com.pdb by searching for their PDB IDs on the RCSB PDB website and downloading the files.

After downloading, upload the PDB files to the /content/pdb_files/ directory in Google Colab as described in the Installation section.
Installation

Set Up Google Colab:

Open a new Google Colab notebook.
Upload the model.py file (available in this repository) to your Colab environment.


Install Dependencies:Run the following commands at the start of your notebook to install the required libraries:
!pip install torch==2.0.0 torch-geometric==2.0.4 biopython==1.79 numpy==1.23.0 pandas==1.5.0 plotly==5.10.0 scikit-learn==1.2.0 transformers openpyxl
!pip install pyg-lib torch-scatter torch-sparse -f https://data.pyg.org/whl/torch-2.0.0+cpu.html


Prepare PDB Files:

Create a directory /content/pdb_files/ in Colab.
Upload your downloaded PDB files (e.g., 1ubq.pdb, 6com.pdb) to this directory.



Usage

Run the Code:

Copy the contents of model.py into a Colab cell and run it.
The script will:
Load and parse PDB files.
Train a GNN model using ESM-2 embeddings.
Perform mutation analysis for residues mutated to A, C, D, and F.
Generate visualizations and download them as HTML files.
Export results to mutation_analysis.xlsx.




View Visualizations:

Open the downloaded HTML files (protein_comparison.html, rmsd_comparison.html, energy_rmsd_comparison.html, ss_changes.html) in a browser to view interactive plots.



Results
The project analyzes the effects of mutating a residue to Alanine (A), Cysteine (C), Aspartic Acid (D), and Phenylalanine (F). Sample results are as follows:
Mutation Analysis

Mutation to A (Alanine): RMSD = 0.8213 Å, Confidence = 98.50%, Energy Difference = 0.00 kcal/mol.
Mutation to C (Cysteine): RMSD = 0.7392 Å, Confidence = 98.45%, Energy Difference = 0.00 kcal/mol.
Mutation to D (Aspartic Acid): RMSD = 0.6570 Å, Confidence = 98.60%, Energy Difference = 0.00 kcal/mol.
Mutation to F (Phenylalanine): RMSD = 0.4928 Å, Confidence = 98.55%, Energy Difference = 0.00 kcal/mol.

Secondary Structure Analysis

Original: Helix: 30.00%, Sheet: 20.00%, Coil: 50.00%.
Mutated to A: Helix: 29.50%, Sheet: 20.10%, Coil: 50.40%.
Mutated to C: Helix: 29.70%, Sheet: 20.00%, Coil: 50.30%.
Mutated to D: Helix: 30.10%, Sheet: 19.90%, Coil: 50.00%.
Mutated to F: Helix: 30.20%, Sheet: 19.80%, Coil: 50.00%.

Project Structure

model.py: Main Python script containing the project code.
project_report.pdf: Detailed project report in PDF format.
README.md: This file, providing an overview and instructions.

Future Scope

Fine-tune ESM-2 for better embeddings.
Implement a more accurate energy calculation (e.g., using AMBER force field).
Add heatmaps for pairwise residue distances.
Deploy as a Flask/React web app for interactive use.
Expand the dataset for improved generalization.

Acknowledgments

Thanks to Meta AI for the ESM-2 model (esm2_t12_35M_UR50D).
Thanks to RCSB PDB for providing access to protein structure datasets.
Built using Google Colab, PyTorch, PyTorch Geometric, BioPython, and Plotly.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or contributions, please open an issue on this repository or contact the author via GitHub.
