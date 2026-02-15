# Affine Gap Sequence Alignment  
## Bioinformatics Assignment

---

## 📌 Overview

This project implements a **nucleotide sequence alignment tool** using dynamic programming with an **affine gap penalty** model.

The program reads two DNA sequences from FASTA files and reports the optimal alignment together with the final alignment score.

The implementation follows the classical DP formulation used in standard alignment algorithms and can be compared with results from online resources such as EBI pairwise alignment tools.

---

## 🧬 Algorithm

The alignment is computed using dynamic programming with three matrices to properly support affine gap penalties.

### Affine Gap Model

Gap cost is calculated as:

Gap = gap_open + (k - 1) × gap_extend

where  
- `gap_open` → penalty for starting a gap  
- `gap_extend` → penalty for extending an existing gap  
- `k` → length of the gap  

---

### DP Matrices Used

- **M** → alignment ends in match/mismatch  
- **X** → alignment ends with a gap in sequence 1  
- **Y** → alignment ends with a gap in sequence 2  

This structure allows the algorithm to distinguish whether a gap is newly opened or being extended.

---

## 📥 Input

The program requires:

1. Two FASTA files  
2. Scoring parameters provided through command line arguments:
   - Match score  
   - Mismatch score  
   - Gap opening penalty  
   - Gap extension penalty  

---

## 📤 Output

The program prints:

- Optimal alignment score  
- Aligned sequence 1  
- Aligned sequence 2  

---

## ▶️ How to Run

From the project directory:

python affine-alignment.py seq1.fasta seq2.fasta


You will then be prompted to enter:

Match score:
Mismatch score:
Gap Opening penalty:
Gap Extension penalty:


---

## 🧪 Testing & Validation

The implementation was tested using the following EBI tool:

https://www.ebi.ac.uk/jdispatcher/psa/lalign?stype=dna&gapext=0

### Validation Steps:
1. Enter the same sequences in the EBI LALIGN tool.
2. Use identical scoring parameters.
3. Compare:
   - Highest Waterman–Eggert score
   - Alignment region
   - Gap placement

The alignment score and region matched the EBI output.

---

## ⏱ Time and Space Complexity

- **Time Complexity:** O(nm)  
- **Space Complexity:** O(nm)

Where:
- n = length of sequence 1
- m = length of sequence 2


---

**Assignment 2**  
**Aparna Trivedi**

---


