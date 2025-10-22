🧠 Scopul proiectului

Scopul aplicației este clasificarea automată a companiilor din domeniul asigurărilor în una sau mai multe categorii (etichete) dintr-o taxonomie predefinită.
Modelul analizează descrierile companiilor și determină cât de similar este textul companiei cu fiecare categorie din taxonomie, atribuind etichetele cele mai relevante.

⚙️ Tehnologii folosite

🧩 Python – limbaj principal de procesare

🤖 SentenceTransformer (all-MiniLM-L6-v2) – model de tip transformer pentru obținerea semantic embeddings (reprezentări vectoriale ale textului)

📊 Pandas, NumPy – procesare și analiză de date

🔥 PyTorch – pentru calculul similarităților vectoriale

📈 Matplotlib, Seaborn – vizualizări grafice și analize de praguri

📘 Excel / CSV – import/export de date și rezultate

🧩 Structura generală a codului

Programul e împărțit în 11 părți logice, fiecare clar separată și documentată în consolă.

Parte	Descriere
1. Loading data	Se încarcă fișierele de intrare: ml_insurance_challenge.csv (companii) și insurance_taxonomy.xlsx (taxonomie).
2. Preparing text	Se combină mai multe câmpuri textuale (descriere, taguri, sector etc.) într-un singur text per companie.
3. Creating embeddings	Se folosește modelul all-MiniLM-L6-v2 pentru a genera vectori numerici pentru fiecare companie și etichetă din taxonomie.
4. Calculating similarities	Se calculează produsul scalar dintre vectorii companiilor și ai taxonomiei → matrice de similaritate semantică.
5. Analyzing threshold	Se testează mai multe praguri (0.3–0.8) pentru a înțelege cum afectează acoperirea și numărul de etichete per companie. Se generează grafice: threshold_analysis.png.
6. Classifying companies	Se selectează etichetele cu similaritate peste un prag (default 0.5) și se salvează top 3 etichete pentru fiecare companie.
7. Classification examples	Se afișează primele 10 companii cu etichetele atribuite și scorurile de similaritate.
8. Validation strategy	Se extrage un eșantion de 50 companii pentru validare manuală și se salvează în manual_validation_sample.xlsx.
9. Label distribution	Se numără etichetele cel mai frecvent atribuite, cu grafice (label_distribution.png).
10. Exporting results	Se creează fișiere de ieșire: company_list_classified.csv (rezumat), classification_details.csv (detaliat).
11. Summary report	Se afișează statistici agregate: acoperire, scoruri medii, top etichete, etc.
