Project Goal

The goal of this application is the automatic classification of insurance companies into one or more predefined categories (labels) from a given taxonomy.
The model analyzes each company’s textual description and determines how semantically similar it is to each taxonomy category, assigning the most relevant labels accordingly.

Technologies Used

Python – main programming and data processing language

SentenceTransformer (all-MiniLM-L6-v2) – transformer-based model for generating semantic embeddings (vector representations of text)

Pandas, NumPy – for data processing and analysis

PyTorch – used for vector similarity computations

Matplotlib, Seaborn – for graphical visualizations and threshold analysis

Excel / CSV – for data import and export of results

General Code Structure

The program is divided into 11 logical parts, each clearly separated and documented in the console output.

Part	Description
Loading data	Loads the input files: ml_insurance_challenge.csv (companies) and insurance_taxonomy.xlsx (taxonomy).
Preparing text	Combines multiple textual fields (description, tags, sector, etc.) into a single text string per company.
Creating embeddings	Uses the all-MiniLM-L6-v2 model to generate numerical embeddings for both companies and taxonomy labels.
Calculating similarities	Computes the dot product between company vectors and taxonomy vectors to create a semantic similarity matrix.
Analyzing threshold	Tests several thresholds (0.3–0.8) to understand how they affect label coverage and number of labels per company. Generates the file threshold_analysis.png.
Classifying companies	Selects labels with similarity scores above a threshold (default 0.5) and saves the top 3 labels for each company.
Classification examples	Displays the first 10 companies with their assigned labels and similarity scores.
Validation strategy	Extracts a sample of 50 companies for manual validation and saves it in manual_validation_sample.xlsx.
Label distribution	Counts the most frequently assigned labels and visualizes them in label_distribution.png.
Exporting results	Creates output files: company_list_classified.csv (summary) and classification_details.csv (detailed).
Summary report	Displays aggregate statistics such as coverage rate, average similarity scores, and top labels.
