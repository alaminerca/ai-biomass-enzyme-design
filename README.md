```markdown
#  AI-Driven Enzyme Design for Biomass Deconstruction

This repository contains our collaborative summer camp project focused on generating and optimizing novel enzymes for the breakdown of aquatic biomass (e.g., algae) using AI techniques, 3D structure prediction, and molecular docking simulations.



##  Folder Structure



 ai-biomass-enzyme-design/
│
├── data/                  # Input datasets (enzyme families, EC numbers, raw sequences)
├── generated\_sequences/   # AI-generated enzyme sequences (.fasta)
├── structures/            # 3D predicted enzyme structures (.pdb)
├── ligands/               # Ligand molecules (e.g., cellobiose, alginate) in .pdbqt format
├── receptors/             # Prepared enzyme files for docking (.pdbqt)
├── poses/                 # Docking output poses for each receptor-ligand pair
├── scores/                # Docking scores, BLAST output, and summary files (.csv, .xml)
├── plots/                 # Visualizations (AA distribution, structure previews)
├── notebooks/             # Jupyter Notebooks for each project step
└── README.md              # This file





##  Project Progress Checklist

| Step | Description | Status |
|------|-------------|--------|
|  Problem Framing | Define objective and questions | ✅ Done |
|  Decoder Selection | Choose model to generate sequences (ProGen2) | ✅ Done |
|  Enzyme Curation | Select relevant enzyme families (GH, PL, CE...) + EC numbers | ✅ Done |
|  Sequence Generation | Use ProGen2 to generate new enzymes | ✅ Done |
|  Cleaning + Stats | Clean output and plot sequence statistics | ✅ Done |
|  Sequence Evaluation | Run BLAST to identify similarity | ✅ Done |
|  Select Top Candidates | Extract top hits per family | ✅ Done |
|  Structure Prediction | Predict 3D structure with AlphaFold/ColabFold | ✅ Done |
|  Ligand Preparation | Convert ligands to .pdbqt (Open Babel) | ✅ Done |
|  Receptor Prep | Convert enzymes to .pdbqt | ✅ Done |
|  Docking | Run AutoDock Vina on each pair | ⏳ In Progress |
|  Post-analysis | Rank and interpret results | ⏳ Upcoming |
|  Final Report / Poster | Assemble results and write report | ⏳ Upcoming |

---

##  Team

- https://github.com/alaminerca  
- https://github.com/ahmedbahaj

---

##  Technologies Used

- **ProGen2** – Protein generation using pretrained transformer models  
- **AlphaFold / ColabFold** – 3D structure prediction  
- **AutoDock Vina** – Molecular docking simulation  
- **Open Babel** – Molecule format conversion  
- **BLAST+** – Similarity search and validation  
- **Py3Dmol / Matplotlib** – Visualization and statistics  
- **Python 3.8+, Biopython, Pandas, NumPy, etc.**

---

##  How to Run Locally

```bash
# Clone the repository
git clone https://github.com/alaminerca/ai-biomass-enzyme-design.git
cd ai-biomass-enzyme-design

# Recommended: setup virtual environment
python3 -m venv env
source env/bin/activate

# Install required Python packages
pip install -r requirements.txt
````

---

##  References & Acknowledgments

* [ProGen2 paper](https://www.cell.com/action/showPdf?pii=S2405-4712%2823%2900272-7)
* [AlphaFold/ColabFold](https://github.com/sokrypton/ColabFold)
* [AutoDock Vina](https://github.com/ccsb-scripps/AutoDock-Vina)
* [BLAST+ Toolkit](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download)

> This project is conducted as part of a **summer AI camp**, to explore applications of deep learning in bioinformatics and enzyme engineering.

---

## Contribution Guide

* Fork and clone the repo.
* Make changes in a dedicated branch.
* Submit a pull request with clear comments.
* Keep notebooks numbered and well-documented.


