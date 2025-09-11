Airline Passenger Reviews Sentiment & Amenity Analysis
This project investigates airline passenger satisfaction through a dual-segmentation lens, analyzing how seating class and passenger type jointly influence experience quality. It combines sentiment analysis of passenger reviews with a statistical evaluation of amenity scores to uncover where airlines excel, where they falter, and how different passenger segments respond.
📊 Overview
The project is divided into two core components:
- Sentiment Analysis
A neural network is trained to classify passenger sentiment based on review text, using seating class and passenger type as contextual features. The goal is to predict whether a passenger would recommend the airline.
- Amenity Score Evaluation
Passenger satisfaction is further analyzed across five key amenities: Ground Service, Entertainment, Seat Comfort, Food & Beverages, and In-Flight Staff. The aim is to identify patterns and performance gaps across different passenger segments.
🎯 Objectives
- Evaluate satisfaction and variability across seating classes and passenger types
- Analyze performance of core amenities using distributional and statistical metrics
- Identify high-performing and high-risk segment-amenity combinations
- Translate findings into actionable recommendations for service design and operational strategy
🧠 Sentiment Model
- Input: Cleaned passenger reviews, seating class, and passenger type
- Output: Binary classification (Recommended vs. Not Recommended)
- Architecture: Feedforward neural network built with PyTorch and wrapped using Skorch
- Training Strategy: Early stopping and scoring callbacks for model tuning
- Evaluation Metrics: Accuracy, F1 score, precision, recall, ROC-AUC, and Brier score
📈 Amenity Analysis
- Segmentation: Passengers grouped by seating class (Economy, Premium, Business, First) and type (Solo, Couple, Family, Professional)
- Metrics: Mean, median, standard deviation, MAD, IQR, and distributional shape
- Statistical Testing: Kruskal-Wallis and Dunn’s tests used to identify significant differences across segments
- Narrative Synthesis: Insights translated into stakeholder-ready summaries and strategic recommendations
📁 Dataset
- Source: Skytrax
- Airlines: Top 10 airlines of 2024
- Variables Used:
- Reviews: Free-text passenger feedback
- Class: Seating tier
- Type: Passenger travel type
- Recommended: Boolean indicator of loyalty
- Amenity Scores: Ratings for Ground Service, Entertainment, Seat Comfort, Food & Beverages, and In-Flight Staff
Additional variables such as travel period and overall rating were collected but not used in the current analysis. They are retained for future evaluation.
🧹 Data Preprocessing
- Removed reviews with missing text
- Normalized and tokenized review content using NLTK and spaCy
- Applied negation marking and contraction expansion
- Converted categorical variables to numeric formats
- Equalized list lengths across all features
- Applied statistical cleaning to amenity scores
🔍 Key Insights
- Ground Service is consistently the weakest amenity, with high variability across all classes and types
- Entertainment emerges as the most stable and well-rated amenity, especially among Solo and Professional travelers
- Seat Comfort improves steadily with class, peaking in First Class with minimal variability
- Staff satisfaction varies sharply by passenger type, with Families and Couples showing elevated inconsistency
- Food & Beverages perform moderately across tiers, with Business Class offering the most balanced experience
💡 Strategic Recommendations
- Prioritize Ground service improvements across all tiers
- Reinforce Entertainment offerings with personalization and loyalty integration
- Standardize Staff delivery for group travelers
- Enhance Comfort in mid-tier cabins to boost perceived value
- Target Solo travelers for loyalty and upsell opportunities
- Refine operational support for Professional travelers seeking efficiency
⚠️ Limitations
- Reviews are self-reported and may contain bias
- Only English-language reviews were used
- Seating class and passenger type were inferred from structured metadata
📚 Citation
This project uses publicly available data from Skytrax for academic purposes under fair use. A-Z Airline reviews - SKYTRAX. (2025). SKYTRAX. https://www.airlinequality.com/review-pages/a-z-airline-reviews/
🛠️ Tools Used
- Python
- PyTorch & Skorch (Neural Network Modeling)
- NLTK & spaCy (Text Preprocessing)
- Pandas & NumPy (Data Handling)
- SciPy & Statsmodels (Statistical Testing)
- Scikit-learn (Model Evaluation & Metrics)
- Seaborn & Matplotlib (Visualization)
- BeautifulSoup & Requests (Web Scraping)
