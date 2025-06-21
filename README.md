#Aspect-Based Sentiment Analysis


Project Overview
This project performs Aspect-Based Sentiment Analysis (ABSA) using zero-shot and few-shot learning with various Llama models on SemEval datasets (laptops and restaurants from 2014, 2015, and 2016). Performance is evaluated using accuracy and F1-score.

Features
Data Preprocessing: Converts XML SemEval datasets to CSV, extracting sentences, aspect terms, and sentiments.

Zero-Shot Analysis: Direct sentiment prediction by Llama models.

Few-Shot Analysis: Sentiment prediction enhanced with in-context examples.

Model Support: Utilizes Llama-3 and Llama-3.1 series models via Hugging Face.

Evaluation: Calculates accuracy and weighted F1-score.

Data Preprocessing
XML data (SemEval 2014, 2015, 2016) is parsed into CSV files with columns: sentence, aspect_term, sentiment, from, to. The script automatically handles two XML structures (aspectTerms and Opinions).

Sentiment Analysis
Two approaches are implemented:

Zero-Shot: Models classify sentiment based on instruction and input.

Few-Shot: Models classify sentiment with a few examples provided in the prompt.

Both methods use the Hugging Face Inference Client to interact with Llama models, with temperature=0.0 for deterministic output.

Evaluation Metrics
Model performance is assessed using:

Accuracy: Percentage of correct predictions.

F1-Score (Weighted): Harmonic mean of precision and recall, weighted by class support.

Getting Started
Prerequisites: Python 3.8+, pip, Hugging Face API token.

Installation:

git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
python -m venv venv
source venv/bin/activate
pip install huggingface_hub scikit-learn

Data Setup: Place raw XML SemEval datasets into data/raw/.

Usage:

Open main.ipynb with jupyter notebook main.ipynb.

Run the "DATA PREPROCESSING" cell.

Replace "YOUR HUGGINGFACE TOKEN" in "ZERO SHOT" and "FEW SHOT" cells.

Run "ZERO SHOT" and "FEW SHOT" cells to execute analysis and view results.

Results
Output in the console will show accuracy and F1-score for each model on each dataset.

Contributing
Contributions are welcome. Please open issues or submit pull requests.

License
This project is licensed under the MIT License.
