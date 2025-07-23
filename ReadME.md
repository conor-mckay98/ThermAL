ThermAL



ThermAL is a desktop GUI tool for predicting regions that stabilise amyloid fibrils.



How ThermAL was created is outlined in McKay et al 2025.



NOTE: The feature extraction step can be time limiting for larger sequences. Thees features are not limited to ThermAL and can be used for other machine learning tasks too!



It takes one or more FASTA sequences as input, generates all single–residue variants, computes physicochemical features (AAC, DPC, sliding‐window AUC), feeds them into a pre-trained Random Forest model, and finally produces many files but the important ones are:



Predicted\_fitness\_with\_1\_letter\_mutations.xlsx



heatmap\_simple.xlsx



heatmap.png



sliding\_window.xlsx



sliding\_window\_with\_foldx.png



All outputs are written into per-job directories named after each input sequence.



📦 Requirements

Python 3.8+



Pandas



NumPy



SciPy



scikit-learn



seaborn



matplotlib



Pillow



joblib



Tkinter



You can install most dependencies with:



bash

Copy

Edit

pip install pandas numpy scipy scikit-learn seaborn matplotlib pillow joblib



📁 Project Structure

/ThermAL

│

├── required\_docs/                  ← precomputed resources

│   ├── 3\_B\_Atlas.xlsx

│   ├── 3\_BT\_Atlas.xlsx

│   ├── … (other atlas files)

│   └── ThermAL.joblib

│

├── ThermAL.png                     ← logo displayed in GUI

├── ThermAL.ipynb                  ← main script (your Python file)

└── README.md                       ← this file



^Please save atlases and ThermAL into new folder required\_docs

🚀 Usage



Ensure the required\_docs/ folder (with all .xlsx atlases and model file) is present.



Run:

Open the notebook -> install dependencies -> Run ThermAL

In the GUI:



Click Select FASTA File and choose your .fasta or .fa file.



Click Run Analysis.



Watch the progress bars as AAC/DPC and feature‐processing steps execute.



When complete, you’ll find one subfolder per sequence in the working directory, each containing exactly the five output files.



🔍 Outputs

Inside each job folder (named after your FASTA header), you’ll get:



Predicted\_fitness\_with\_1\_letter\_mutations.xlsx

Full table of variants, model predictions, and one-letter mutation codes.



heatmap\_simple.xlsx

Pivot table of mean predicted fitness per mutation/position.



heatmap.png

Visual heatmap (lightskyblue⇢white⇢red) with wild-type cells bordered in black. This may be squashed for larger sequences but can be replotted using the data present in heatmap\_simple.xlsx



sliding\_window.xlsx

Centered 5-residue sliding‐window average of the pivot table means.



sliding\_window\_with\_foldx.png

Plot of the (–1×) sliding window average highlighting stabilising regions. This may be squashed for larger sequences but can be replotted using the data present in sliding\_window.xlsx





Any problems I am more than happy to chat: conor\_mckay98@aol.com (PhD student @ University of Leeds/AstraZeneca)

