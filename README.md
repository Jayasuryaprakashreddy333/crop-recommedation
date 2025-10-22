# Crop Recommendation System

## Overview
The Crop Recommendation System is a machine learning-powered application designed to assist farmers and agricultural specialists in selecting the most suitable crops based on soil characteristics, environmental parameters, and nutrient levels. By leveraging predictive models, the system analyzes inputs such as Nitrogen (N), Phosphorus (P), Potassium (K), temperature, humidity, pH, and rainfall to provide data-driven recommendations. This promotes sustainable farming practices, optimizes resource use, and enhances productivity.

This project draws inspiration from popular open-source implementations on GitHub, such as those using Random Forest classifiers and datasets from Kaggle. It includes features for crop, fertilizer, and pest management recommendations.

## Features
- **Crop Recommendation**: Input soil nutrients (N, P, K), temperature, humidity, pH, and rainfall to get the top recommended crops (e.g., rice, maize, wheat).
- **Fertilizer Suggestions**: Tailored advice based on crop type and soil needs.
- **Pest Management**: Region-specific pesticide recommendations for common pests.
- **User-Friendly Web Interface**: Built with Flask or Streamlit for easy input and visualization.
- **Model Accuracy**: Achieves high precision (typically 95-99% with Random Forest) on test datasets.
- **Sustainability Focus**: Reduces chemical overuse and water waste through precise insights.

## Dataset
The system uses the [Crop Recommendation Dataset](https://www.kaggle.com/atharvaingle/crop-recommendation-dataset) from Kaggle, which includes:
- 2,200+ samples across 22 crop types.
- Features: N, P, K (soil nutrients), temperature (°C), humidity (%), pH, rainfall (mm).
- Labels: Crop names (e.g., apple, banana, cotton).

Sample data structure:

| N   | P   | K   | temperature | humidity | ph  | rainfall | label    |
|-----|-----|-----|-------------|----------|-----|----------|----------|
| 90  | 42  | 43  | 20.879744  | 82.002744| 6.502985 | 202.935536 | rice    |
| 85  | 58  | 41  | 21.770462  | 80.319644| 7.03896  | 226.655537 | maize   |
| 60  | 48  | 27  | 23.004459  | 93.594779| 5.52705  | 145.060162 | chickpea|

## Technologies Used
- **Programming Language**: Python 3.8+
- **Machine Learning**: Scikit-learn (Random Forest Classifier, Decision Tree, SVM, KNN, Gradient Boosting)
- **Data Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Web Framework**: Flask or Streamlit for the UI
- **Model Persistence**: Joblib or Pickle for saving trained models
- **Other**: Bootstrap for frontend styling

## Installation
1. **Clone the Repository**:
   ```
   git clone https://github.com/yourusername/crop-recommendation-system.git
   cd crop-recommendation-system
   ```

2. **Set Up Virtual Environment**:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:
   Create and run `requirements.txt`:
   ```
   pip install -r requirements.txt
   ```
   Sample `requirements.txt`:
   ```
   pandas==1.5.3
   numpy==1.24.3
   scikit-learn==1.3.0
   flask==2.3.3
   matplotlib==3.7.2
   seaborn==0.12.2
   joblib==1.3.1
   ```

4. **Download Dataset**:
   Place `Crop_recommendation.csv` in the root directory (download from Kaggle link above).

5. **Train the Model** (if needed):
   Run the training script:
   ```
   python train_model.py
   ```
   This generates `crop_model.pkl`.

## Usage
1. **Run the Application**:
   ```
   python app.py  # For Flask
   # Or
   streamlit run app.py  # For Streamlit
   ```

2. **Access the Interface**:
   - Open `http://localhost:5000` (Flask) or `http://localhost:8501` (Streamlit).
   - Enter parameters (e.g., N=90, P=42, K=43, temp=20.88, humidity=82, pH=6.5, rainfall=202.94).
   - Receive recommendations like "Recommended Crop: Rice" with confidence scores.

3. **Example Output**:
   - Top Crops: Rice (98% suitability), Jute (92%).
   - Fertilizer: Increase Nitrogen by 10-15 kg/ha.
   - Pest Alert: Monitor for rice blast; recommend fungicide X.

For fertilizer or pest modules, select the respective tabs and input crop/region details.

## Model Training and Evaluation
- **Preprocessing**: Handle missing values, normalize features using StandardScaler.
- **Models Compared**:
  | Model                  | Accuracy (%) |
  |------------------------|--------------|
  | Random Forest         | 99.2        |
  | Decision Tree         | 99.4        |
  | SVM                   | 97.8        |
  | KNN                   | 97.6        |
  | Gradient Boosting     | 98.5        |
- **Best Model**: Random Forest due to robustness and low overfitting.
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1-Score (all >0.98 on balanced dataset).
- Training script (`train_model.py`) includes cross-validation (5-fold) for reliability.

## Future Enhancements
- Integrate real-time weather APIs (e.g., OpenWeatherMap) for dynamic inputs.
- Support more crops/regions with expanded datasets.
- Add mobile app compatibility.
- Incorporate computer vision for soil image analysis.
- Deploy on cloud (Heroku/AWS) for scalability.

## Contributing
Contributions are welcome! To get started:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/amazing-feature`).
3. Commit changes (`git commit -m 'Add amazing feature'`).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request.

Please ensure code follows PEP 8 standards and includes tests.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Dataset: [Kaggle Crop Recommendation Dataset](https://www.kaggle.com/atharvaingle/crop-recommendation-dataset).
- Inspired by projects like [Harsha-G/Crop-Recommendation-using-Machine-Learning](https://github.com/Harsha-G/Crop-Recommendation-using-Machine-Learning) and [vsatyakiran/Smart-Harvest](https://github.com/vsatyakiran/Smart-Harvest).
- Developed for educational and practical use in precision agriculture.

For issues or questions, open a GitHub issue or contact the maintainer.

---

*Note: This README is a generalized template based on common crop recommendation projects. Customize it for your specific implementation.*
