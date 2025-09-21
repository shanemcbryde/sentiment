# ✈️ Airline Passenger Reviews Sentiment & Amenity Analysis

This project investigates airline passenger satisfaction through a dual-segmentation lens, analyzing how seating class and passenger type jointly influence experience quality. It combines sentiment analysis of passenger reviews with a statistical evaluation of amenity scores to uncover where airlines excel, where they falter, and how different passenger segments respond.

## 📊 Overview

The project is divided into two core components:

1. **Sentiment Analysis**  
   A neural network is trained to classify passenger sentiment based on review text, using seating class and passenger type as contextual features. The goal is to predict whether a passenger would recommend the airline.

2. **Amenity Score Evaluation**  
   Passenger satisfaction is further analyzed across five key amenities: Ground Service, Entertainment, Seat Comfort, Food & Beverages, and In-Flight Staff. The aim is to identify patterns and performance gaps across different passenger segments.

## 🎯 Objectives

- Evaluate satisfaction and variability across seating classes and passenger types  
- Analyze performance of core amenities using distributional and statistical metrics  
- Identify high-performing and high-risk segment-amenity combinations  
- Translate findings into actionable recommendations for service design and operational strategy  

## 🧠 Sentiment Model

- **Input:** Cleaned passenger reviews, seating class, and passenger type  
- **Output:** Binary classification (Recommended vs. Not Recommended)  
- **Architecture:** Feedforward neural network built with PyTorch and wrapped using Skorch  
- **Training Strategy:** Early stopping and scoring callbacks for model tuning  
- **Evaluation Metrics:** Accuracy, F1 score, precision, recall, ROC-AUC, and Brier score  

## 📈 Amenity Analysis

- **Segmentation:** Passengers grouped by seating class (Economy, Premium, Business, First) and type (Solo, Couple, Family, Professional)  
- **Metrics:** Mean, median, standard deviation, MAD, IQR, and distributional shape  
- **Statistical Testing:** Kruskal-Wallis and Dunn’s tests used to identify significant differences across segments  
- **Narrative Synthesis:** Insights translated into stakeholder-ready summaries and strategic recommendations  

## 📁 Dataset

- **Source:** [Skytrax](https://www.airlinequality.com)  
- **Airlines:** Top 10 airlines of 2024  
- **Variables Used:**
  - `Reviews`: Free-text passenger feedback  
  - `Class`: Seating tier  
  - `Type`: Passenger travel type  
  - `Recommended`: Boolean indicator of loyalty  
  - `Amenity Scores`: Ratings for Ground Service, Entertainment, Seat Comfort, Food & Beverages, and In-Flight Staff  

Additional variables such as travel period and overall rating were collected but not used in the current analysis. They are retained for future evaluation.

## 🧹 Data Preprocessing

- Removed reviews with missing text  
- Normalized and tokenized review content using NLTK and spaCy  
- Applied negation marking and contraction expansion  
- Converted categorical variables to numeric formats  
- Equalized list lengths across all features  
- Applied statistical cleaning to amenity scores  

## 🔍 Key Insights

- Ground Service is consistently the weakest amenity, with high variability across all classes and types  
- Entertainment emerges as the most stable and well-rated amenity, especially among Solo and Professional travelers  
- Seat Comfort improves steadily with class, peaking in First Class with minimal variability  
- Staff satisfaction varies sharply by passenger type, with Families and Couples showing elevated inconsistency  
- Food & Beverages perform moderately across tiers, with Business Class offering the most balanced experience  

## 💡 Strategic Recommendations

- Prioritize Ground service improvements across all tiers  
- Reinforce Entertainment offerings with personalization and loyalty integration  
- Standardize Staff delivery for group travelers  
- Enhance Comfort in mid-tier cabins to boost perceived value  
- Target Solo travelers for loyalty and upsell opportunities  
- Refine operational support for Professional travelers seeking efficiency  

## ⚠️ Limitations

- Passenger reviews are inherently subjective and reflect personal experiences, expectations, and emotions. While this makes them valuable for sentiment analysis, it also means they may not represent a balanced or comprehensive view of all passengers.
- Only English-language reviews were used, which may exclude perspectives from non-English-speaking travelers.
- Seating class and passenger type were extracted from structured metadata on the review pages, not explicitly stated by passengers in the review text.  

## 🛠️ Tools Used

[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat)](https://pytorch.org) [![Skorch](https://img.shields.io/badge/Skorch-Model_Wrapper-blue?style=flat)](https://skorch.readthedocs.io/) [![Python](https://img.shields.io/badge/Python-3776AB?style=flat)](https://python.org) [![NLTK](https://img.shields.io/badge/NLTK-Text_Processing-green?style=flat)](https://www.nltk.org) [![spaCy](https://img.shields.io/badge/spaCy-NLP-09A3D5?style=flat)](https://spacy.io) [![Pandas](https://img.shields.io/badge/Pandas-Data_Handling-150458?style=flat)](https://pandas.pydata.org) [![NumPy](https://img.shields.io/badge/NumPy-Numerical_Computing-013243?style=flat)](https://numpy.org) [![SciPy](https://img.shields.io/badge/SciPy-Statistical_Testing-blue?style=flat)](https://scipy.org) [![Statsmodels](https://img.shields.io/badge/Statsmodels-Post_Hoc_Analysis-darkgreen?style=flat)](https://www.statsmodels.org) [![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-Metrics-F7931E?style=flat)](https://scikit-learn.org) [![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat)](https://matplotlib.org) [![Seaborn](https://img.shields.io/badge/Seaborn-Statistical_Plots-76B900?style=flat)](https://seaborn.pydata.org) [![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-Web_Scraping-8B008B?style=flat)](https://www.crummy.com/software/BeautifulSoup/) [![Requests](https://img.shields.io/badge/Requests-HTTP_Client-20232A?style=flat)](https://docs.python-requests.org)

## 📚 Citation

This project uses publicly available data from Skytrax for academic purposes under fair use.

Skytrax. (2025). *A-Z Airline Reviews*. Retrieved from [https://www.airlinequality.com/review-pages/a-z-airline-reviews/](https://www.airlinequality.com/review-pages/a-z-airline-reviews/)

## 📖 References

### Third-Party Code

- Tam, A. (2023, April 7). *Use PyTorch Deep Learning Models with scikit-learn*. Guiding Tech Media. Retrieved from [https://machinelearningmastery.com/use-pytorch-deep-learning-models-with-scikit-learn/](https://machinelearningmastery.com/use-pytorch-deep-learning-models-with-scikit-learn/)

- GeeksforGeeks. (2024, December 27). *How to remove string accents using Python 3*. Sanchhaya Education Pvt. Ltd. Retrieved from [https://www.geeksforgeeks.org/how-to-remove-string-accents-using-python-3/](https://www.geeksforgeeks.org/how-to-remove-string-accents-using-python-3/)
