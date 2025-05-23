Protein Folding AI

📋 Project Overview
Protein Folding AI is a B.Tech AI & Data Science project focused on predicting protein structures and analyzing the effects of mutations using Graph Neural Networks (GNNs) and ESM-2 embeddings. Proteins are modeled as graphs, with amino acid residues as nodes and spatial proximity defining edges. The project leverages ESM-2 embeddings for enhanced biological feature representation and employs GNNs to predict 3D structures. Key features include mutation analysis, interactive visualizations, and Excel export for results.
This project was completed and documented on 09:45 PM IST on Friday, May 23, 2025.

✨ Features

Protein Structure PredictionUses GNNs to predict 3D coordinates of protein residues with high accuracy.

ESM-2 EmbeddingsIntegrates esm2_t12_35M_UR50D embeddings for rich biological feature representation.

Mutation AnalysisComputes the following metrics for mutations:

RMSD (Root Mean Square Deviation)
Energy Differences (via a simplified Lennard-Jones potential)
Secondary Structure Changes (using DSSP)
Confidence Scores (based on prediction variance)


Interactive VisualizationsGenerates Plotly-based HTML visualizations:

protein_comparison.html: Full-screen 3D comparison of original (blue) and mutated (red) structures.
rmsd_comparison.html: Bar chart displaying RMSD values.
energy_rmsd_comparison.html: Dual-axis chart comparing RMSD and energy differences.
ss_changes.html: Grouped bar chart showing secondary structure changes.


Excel ExportExports results (RMSD, confidence scores, energy differences, secondary structure percentages) to mutation_analysis.xlsx.




📥 Download Dataset
To run this project, you’ll need protein structure data in PDB format. The dataset can be downloaded from the RCSB Protein Data Bank (PDB), a repository of experimentally determined 3D structures of proteins.

RCSB PDB Download Link:  

Access the RCSB PDB File Download Services for individual downloads.
Direct coordinate files are available at https://files.rcsb.org/pub/pdb/data/structures/divided/pdb.


Batch Download:For downloading multiple PDB files, use the RCSB PDB Batch Download Service, which provides a shell script for efficient batch downloads.

Example PDB Files:For testing, download small protein structures such as 1ubq.pdb (ubiquitin) or 6com.pdb by searching their PDB IDs on the RCSB PDB website and downloading the files.


After downloading, upload the PDB files to the /content/pdb_files/ directory in Google Colab as described in the Installation section.

🚀 Installation

Set Up Google Colab  

Open a new Google Colab notebook.
Upload the model.py file (available in this repository) to your Colab environment.


Install DependenciesRun the following commands at the start of your notebook to install the required libraries:
!pip install torch==2.0.0 torch-geometric==2.0.4 biopython==1.79 numpy==1.23.0 pandas==1.5.0 plotly==5.10.0 scikit-learn==1.2.0 transformers openpyxl
!pip install pyg-lib torch-scatter torch-sparse -f https://data.pyg.org/whl/torch-2.0.0+cpu.html


Prepare PDB Files  

Create a directory /content/pdb_files/ in Colab.
Upload your downloaded PDB files (e.g., 1ubq.pdb, 6com.pdb) to this directory.




🖥️ Usage

Run the Code  

Copy the contents of model.py into a Colab cell and execute it.
The script will perform the following tasks:
Load and parse PDB files.
Train a GNN model using ESM-2 embeddings.
Perform mutation analysis for residues mutated to A (Alanine), C (Cysteine), D (Aspartic Acid), and F (Phenylalanine).
Generate visualizations and download them as HTML files.
Export results to mutation_analysis.xlsx.




View Visualizations  

Open the downloaded HTML files (protein_comparison.html, rmsd_comparison.html, energy_rmsd_comparison.html, ss_changes.html) in a browser to explore interactive plots.




📊 Results
The project analyzes the effects of mutating a residue to four amino acids: Alanine (A), Cysteine (C), Aspartic Acid (D), and Phenylalanine (F). 

📂 Project Structure

model.py: Main Python script containing the project code.
project_report.pdf: Detailed project report in PDF format.
README.md: This file, providing an overview and instructions.


🔮 Future Scope

Fine-Tune ESM-2: Improve embeddings by fine-tuning on specific datasets.
Advanced Energy Calculation: Replace the simplified Lennard-Jones potential with a more accurate force field (e.g., AMBER).
Additional Visualizations: Add heatmaps for pairwise residue distances.
Web Application: Deploy as a Flask/React web app for interactive use.
Expand Dataset: Train on a larger dataset for better generalization.


🙏 Acknowledgments

Meta AI: For the ESM-2 model (esm2_t12_35M_UR50D).
RCSB PDB: For providing access to protein structure datasets.
Tools Used: Google Colab, PyTorch, PyTorch Geometric, BioPython, Plotly.


📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

📬 Contact
For questions, contributions, or feedback

