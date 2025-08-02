Hello team,

Here is a simple guide to run the computational pipeline we built to discover and test a new, AI-generated enzyme. Our project is split into two separate Google Colab notebooks to keep things simple and avoid software conflicts.

You will need to run them in order.

### **Part 1: The "Main Pipeline" Notebook**

**What it does:** This notebook uses an AI model to invent a new enzyme sequence, prepares our target molecule (the ligand), and runs the final docking simulation.

**How to run it:**

1.  **Open the Main\_Pipeline.ipynb notebook** in Google Colab.
    
2.  **Run Cell 1 (Installation):**
    
    *   Just run this cell once. It will install all the necessary software like rdkit and vina. It should take about 2-3 minutes.
        
    *   If numpy error, check the comment in the very first cell
        
3.  **Run Cell 2 (Generate Enzyme Sequence):**
    
    *   This cell uses an AI called ProGen2 to create a brand-new sequence for a Xylanase enzyme.
        
    *   It will automatically validate the sequence to make sure it's a good one.
        
    *   The final output will be a file named validated\_xylanase.fasta.
        
4.  **Run Cell 3 (Prepare Ligand):**
    
    *   This cell prepares our target molecule, Xylobiose. It's very quick.
        
5.  **Run Cell 4 (Download the Sequence):**
    
    *   This is a **manual handoff step**.
        
    *   When you run this cell, a download link will appear. Click it to save the validated\_xylanase.fasta file to your computer.
        
    *   **STOP here and move to Part 2.**
        

### **Part 2: The "Structure Prediction" Notebook**

**What it does:** This notebook's only job is to take our FASTA sequence and predict its 3D protein structure using the official ColabFold tool.

**How to run it:**

1.  **Open the official ColabFold notebook** using this link:
    
    *   [**Official ColabFold: AlphaFold2**](https://www.google.com/url?sa=E&q=https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb)
        
2.  **Input Your Sequence:**
    
    *   In the first cell, you'll see a field called sequence. Delete the example sequence in there.
        
    *   Open the validated\_xylanase.fasta file on your computer with a text editor, copy the long string of letters (the sequence), and paste it into the sequence field.
        
3.  **Run the Cells:**
    
    *   Simply go to the menu and select Runtime -> Run all.
        
    *   This is the longest step and can take **20-40 minutes**. ColabFold is doing a lot of heavy lifting.
        
4.  **Download the Results:**
    
    *   When it's finished, the last cell will automatically zip up all the results and provide a download link. Download this .zip file.
        
5.  **Find the Best Structure:**
    
    *   Unzip the results file on your computer. Inside, you will find several files.
        
    *   Look for the file that has **...rank\_001...** in its name. This is the PDB file for the best, most confident 3D structure.
        

### **Part 3: Back to the "Main Pipeline" Notebook**

**What it does:** This is the final step where we test if our ligand fits into our new enzyme structure.

**How to run it:**

1.  **Go back to your Main\_Pipeline.ipynb notebook.**
    
2.  **Run Cell 5 (Docking & Analysis):**
    
    *   When you run this final cell, it will immediately prompt you to upload a file.
        
    *   Choose the **...rank\_001...pdb** file that you just found from the ColabFold results.
        
3.  **Get the Results!**
    
    *   The notebook will take over, prepare the structure, run the docking simulation with AutoDock Vina, and generate our final results table and plot.
        

If all steps work fine, you will see and output like this:

🔹 \[Step 5/5\] Evaluation: ✅ GOOD BINDING: A favorable interaction is predicted.==================================================🎉🎉🎉 PIPELINE COMPLETE! 🎉🎉🎉==================================================and a plot.