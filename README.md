```markdown
#  AI-Driven Enzyme Design for Biomass Deconstruction

This repository contains our collaborative summer camp project focused on generating and optimizing novel enzymes for the breakdown of aquatic biomass (e.g., algae) using AI techniques, 3D structure prediction, and molecular docking simulations.



##  Folder Structure



 ai-biomass-enzyme-design/
│
├── result_alphafold/      # predicted structure for each sample (detailed summary and graphs)
├── data/                  # Input datasets (enzyme families, EC numbers, raw sequences)
├── data/structures/       # 3D predicted enzyme structures (.pdb)
├── data/ligands/          # Ligand molecules (e.g., cellobiose, alginate) in .pdbqt format
├── data/docking/          # Docking output poses for each receptor-ligand pair
├── results/               # Docking scores and summary files (.csv)
├── plots/                 # Visualizations (heatmap)
├── notebooks/             # Jupyter Notebooks for each project step
└── Final_report.pdf       # final report of the project.
└── README.md              # This file






##  Project Progress Checklist

| Step | Description | Status |
|------|-------------|--------|
|  Problem Framing | Define objective and questions | ✅ Done |
|  Decoder Selection | Choose model to generate sequences (ProGen2) | ✅ Done |
|  Enzyme Curation | Select relevant enzyme families (GH, PL, CE...) + EC numbers | ✅ Done |
|  Sequence Generation | Use ProGen2 to generate new enzymes | ✅ Done |
|  Cleaning + Stats | Clean output and plot sequence statistics | ✅ Done |
|  Sequence Evaluation | AlphaFold | ✅ Done |
|  Select Top Candidates | Extract top hits per family | ✅ Done |
|  Structure Prediction | Predict 3D structure with AlphaFold/ColabFold | ✅ Done |
|  Ligand Preparation | Convert ligands to .pdbqt (Open Babel) | ✅ Done |
|  Receptor Prep | Convert enzymes to .pdbqt | ✅ Done |
|  Docking | Run AutoDock Vina on each pair | ✅ Done |
|  Post-analysis | Rank and interpret results | ✅ Done |
|  Final Report / Poster | Assemble results and write report | Done |

---

##  Team

- https://github.com/alaminerca  
- https://github.com/ahmedbahaj
- http://github.com/nabil-ha

---

##  Technologies Used

- **ProGen2** – Protein generation using pretrained transformer models  
- **AlphaFold / ColabFold** – 3D structure prediction  
- **AutoDock Vina** – Molecular docking simulation  
- **Open Babel** – Molecule format conversion  
- **Google Colab** – High-Performance Computer  
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

# Install required Python packages (all packages will be Installed automatically, in case they did not, run the next this line)
pip install -r requirements.txt
````

---

##  References & Acknowledgments

* [ProGen2 paper](https://www.cell.com/action/showPdf?pii=S2405-4712%2823%2900272-7)
* [AlphaFold/ColabFold](https://github.com/sokrypton/ColabFold)
* [AutoDock Vina](https://github.com/ccsb-scripps/AutoDock-Vina)
* Hugo et al. (202400. Protein Family Sequence Generation through ProGen2 Fine Tuning, Arxiv 2 Jumper, J., et al. (2021).  
* Highly accurate protein structure prediction with AlphaFold. Nature, 596(7873), 583-589.  Mirdita, M., et al. (2022).  
* https://news.engr.psu.edu/2024/molecular-roadblocks-slow-cellulosebreakdown.aspx  
* https://www.frontiersin.org/journals/energyresearch/articles/10.3389/fenrg.2016.00036/fulSupportingDocuments 
* Gemini AI – Google, Claude AI - Anthropic, and ChatGPT – OpenAI, Copilot – Microsoft 
> This project is conducted as part of a **summer AI camp**, to explore applications of deep learning in bioinformatics and enzyme engineering.

---

## Contribution Guide

* Fork and clone the repo.
* Make changes in a dedicated branch.
* Submit a pull request with clear comments.



