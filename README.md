species_id	species	genus	family	class	dna_length_mb	gc_content	mutation_rate	conserved_genes	transposon_pct	mitochondrial_similarity	snp_density	divergence_mya	evolutionary_clade	environmental_pressure_index	effective_population_size
205	Fish_Species_30	Fish_Genus_4	Fish_Family_2	Fish	1791	38.33	2.805	16320	37.49	70.45	1.16	499	Fish	0.75	90681
159	Reptile_Species_29	Reptile_Genus_2	Reptile_Family_8	Reptile	2189	45.92	3.074	16194	41.58	72.83	1.26	499	Reptile	0.42	129823
205	Fish_Species_30	Fish_Genus_4	Fish_Family_2	Fish	1791	38.83	2.861	16320	37.99	70.45	1.32	499	Fish	0.62	90728
205	Fish_Species_30	Fish_Genus_4	Fish_Family_2	Fish	1791	38.69	3.002	16320	38.07	70.45	1.35	499	Fish	0.53	89922
205	Fish_Species_30	Fish_Genus_4	Fish_Family_2	Fish	1791	38.69	3.026	16320	38.59	70.45	1.06	499	Fish	0.69	87898
Above are the first 5 rows of data from the evolution dataset.

Evolution is visible in this dataset through DNA differences between species. Mutation rate, SNP density, and transposons show how DNA changes over time.
Conserved genes indicate natural selection preserving important traits. Mitochondrial similarity and divergence time show common ancestry and evolutionary distance.
Together, these features explain how species slowly change and evolve from shared ancestors.

**Flowchart: DNA Evolution Analysis System**
1. Start GUI
User launches main.py (GUI script).
Tkinter window opens with buttons for different analysis modules.

2. Background & Main Frame Setup
Load background image if available.
Create main frame with buttons for:
Clustering
Dimensionality Reduction
Model Training
Confusion Matrix
Time-Series Analysis
Live Prediction

3. Clustering Module
K-Means / DBSCAN
Call model.run_kmeans() or model.run_dbscan().
Model performs clustering on preprocessed features.
Results displayed via messagebox (number of clusters).

Hierarchical (Dendrogram)
Call model.run_hierarchical().
Generates dendrogram plot.
Opens the saved dendrogram image in default browser.

4. Dimensionality Reduction
PCA / t-SNE
Call model.run_pca() or model.run_tsne().
Reduces high-dimensional DNA features to 2D.
Saves plot and opens in browser.

5. Model Training & Evaluation
Train/Test Accuracy Comparison
Call model.train_test_comparison().
Trains multiple classifiers (RF, SVM, LR, XGBoost) on time-series features.
Displays Train/Test accuracy for each model.

Show Trained Models
Call model.train_classifiers().
Returns list of trained models.

6. Confusion Matrix
Call model.generate_confusion_matrix().
Generate confusion matrix for Random Forest model.
Opens heatmap image in browser.

7. Time-Series Analysis
Decomposition
Call model.perform_decomposition().
Performs seasonal decomposition of selected DNA feature.
Opens decomposition plot in browser.

ARIMA Forecast
Call model.run_arima_forecast().
Forecast future values of selected DNA feature.
Opens forecast plot in browser.

8. Live Prediction
User inputs numeric DNA features in a scrollable form.
Selects a trained model.
Call model.predict_live() to predict species class.
Result displayed in a popup.

9. Exit
User clicks Exit → GUI closes.

**THE WORKFLOW OF THIS PROJECT IS AS FOLLOWS:**
+----------------------------------------------------+
| Load Dataset |
| evolution_time_series_updated.csv |
+----------------------------------------------------+
|
v
+----------------------------------------------------+

Time-Series Feature Engineering
- Rolling averages (3,5) for GC & mutation rate
- Lag features (1,2 periods) for GC & mutation
- Backfill missing values
+----------------------------------------------------+
                      |  
                      v  


+----------------------------------------------------+

Preprocessing & Feature Selection
- Select numeric columns
- Scale features (StandardScaler/MinMaxScaler)
- Encode labels (LabelEncoder)
- Feature selection: ANOVA or Chi-squared
+----------------------------------------------------+
                      |  
                      v  


+----------------------------------------------------+
| ML Tasks |
+----------------------------------------------------+
| 1️⃣ Unsupervised Learning |
| - KMeans Clustering |
| - DBSCAN |
| - Hierarchical Clustering (Dendrogram plot) |
| |
| 2️⃣ Dimensionality Reduction |
| - PCA (2D visualization) |
| - t-SNE (2D visualization) |
| |
| 3️⃣ Supervised Learning |
| - Time-aware Train/Test Split |
| - Models: |
| • Random Forest |
| • SVM |
| • Logistic Regression |
| • XGBoost |
| - Evaluate Accuracy / F1-score |
| - Confusion Matrix Visualization |
| |
| 4️⃣ Time-Series Forecasting & Analysis |
| - Seasonal Decomposition (mutation_rate / GC) |
| - ARIMA Forecasting |
+----------------------------------------------------+
|
v
+----------------------------------------------------+

Outputs
- Cluster Labels (KMeans/DBSCAN)
- Dendrogram Image
- PCA & t-SNE Plots
- Accuracy & Metric Comparison Table
- Confusion Matrix Image
- Time-Series Decomposition Plot
- ARIMA Forecast Plot
- Saved Models for Live Prediction
+----------------------------------------------------+
                      |  
                      v  


+----------------------------------------------------+

Live Prediction (GUI/Web)
- Input: New sample features
- Choose Model (Random Forest / SVM / etc.)
- Output: Predicted Class / Evolution Trend
+----------------------------------------------------+

I have separated the GUI layer and ML logic into different modules. The Tkinter app acts as the
controller and imports the ML functions, which improves maintainability and testability.”

  
