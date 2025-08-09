### **Guide: Multiple Seqs Enzyme Screening Pipeline**

Hello team,

Here is the updated guide for running our new computational pipeline. This version is designed for high-throughput screening. Instead of generating a single AI enzyme, it allows us to test **multiple known enzyme sequences** (from a FASTA file) against a **curated database of relevant ligands**.

Please run the cells in the mutli\_seqs.ipynb in order.

### **Part 1: Setup and Input Preparation**

**What it does:** This part installs all necessary software, creates the folder structure, and prepares all our input files (both enzymes and ligands) for the main analysis.

**How to run it:**

1.  **Run Cell 1 (Installation):**
    
    *   Run this cell once at the start of your session. It installs AutoDock Vina, Open Babel, rdkit, and all other required libraries. This may take several minutes.
        
2.  **Run Cell 1a (Create Directories):**
    
    *   This cell quickly creates all the folders (results, plots, data, etc.) that the pipeline will need.
        
3.  **Run Cell 2 (Inputs & Cleaning):**
    
    *   This is a critical input step. When you run this cell, it will immediately prompt you to **upload your multi-sequence FASTA file** containing all the enzyme sequences you want to test.
        
    *   The script will then automatically clean each sequence to remove non-amino-acid characters, saving a new file named data/cleaned\_enzymes.fasta.
        
4.  **Run Cell 3 (Ligand Preparation):**
    
    *   This cell is fully automated. It uses our self-contained database of 7 key ligands (Xylobiose, Ferulic Acid, etc.) and prepares each one for docking, saving them as .pdbqt files in the data/ligands/ folder.
        
5.  **Run Cell 4 (Automatic FASTA Splitting):**
    
    *   This is the final preparation step. The script takes your cleaned\_enzymes.fasta file and automatically splits it into individual FASTA files, one for each enzyme.
        
    *   It then zips them all into a single file named individual\_fasta\_sequences.zip and provides a download link.
        
    *   **Click the link to download this .zip file to your computer.**
        
    *   **STOP here and move to Part 2.**
        

### **Part 2: Structure Prediction with ColabFold (Batch)**

**What it does:** This is the manual handoff step where we use the official ColabFold Batch tool to predict the 3D structure for every one of our enzyme sequences.

**How to run it:**

1.  **Unzip the File:** On your computer, unzip the individual\_fasta\_sequences.zip file. This will give you a folder containing many individual .fasta files.
    
2.  **Open ColabFold Batch:**
    
    *   Use this specific link: [**ColabFold\_batch.ipynb**](https://www.google.com/url?sa=E&q=https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/ColabFold_batch.ipynb)
        
3.  **Configure and Run:**
    
    *   In the ColabFold notebook's file browser (left-hand side), click the "Upload" button and **upload the entire folder** of individual FASTA files.
        
    *   In the first code cell, find the line input\_dir = 'input'.
        
    *   **Change this line** to point to your uploaded folder. For example, if your folder is named split\_fasta\_files, the line should be: input\_dir = 'split\_fasta\_files'
        
    *   Set a jobname (e.g., algae\_enzyme\_screen).
        
    *   From the top menu, select **Runtime -> Run all**.
        
4.  **Wait and Download:**
    
    *   This is the longest step and can take a considerable amount of time. The notebook will process each sequence file in the folder one by one.
        
    *   When it is finished, a .zip file containing all the results (e.g., algae\_enzyme\_screen.result.zip) will be downloaded to your computer automatically.
        
5.  **Find the Best Structures:**
    
    *   Unzip the results file on your computer. Inside, you will find a folder for each enzyme, containing multiple PDB files and a JSON file with quality scores.
        

### **Part 3: Final Docking and Analysis**

**What it does:** This is the final step where we perform a "many-to-many" docking analysis, testing every ligand against every high-quality enzyme structure.

**How to run it:**

1.  **Go back to your** mutli\_seqs**.ipynb.**
    
2.  **IMPORTANT - Quality Control:**
    
    *   Before running the final cell, you must decide which predicted structures are good enough to use.
        
    *   In the ColabFold results folders, open the JSON files (e.g., ...scores.json). Look at the plddt score for the rank\_001 model of each enzyme.
        
    *   **Only proceed with structures where the pLDDT score is > 70.** This ensures your docking results are scientifically meaningful. Using low-quality structures will produce invalid data.
        
3.  **Run Cell 5 (Docking & Analysis):**
    
    *   When you run this final cell, it will prompt you to upload files.
        
    *   Select and upload **only the high-quality PDB files** (e.g., the ...rank\_001...pdb files for the enzymes that had a pLDDT score > 70).
        
4.  **Get the Results!**
    
    *   The notebook will take over, automatically running a docking simulation for every protein-ligand combination.
        
    *   When finished, it will generate the final, comprehensive results:
        
        *   A **summary table** printed directly in the notebook.
            
        *   A **color-coded heatmap** visualizing the binding affinities.
            
        *   Saved .csv and .png files in the results/ and plots/ folders.