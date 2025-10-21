# Satellite-Based Cloud Observation and Rainfall Nowcasting Using Computer Vision

**Computer Vision Course – Fall 2025**  
BSc (Hons) in Computer Science  
**Research Proposal**

---

## 1. Title & Team

**Project Title:** Satellite-Based Cloud Observation and Rainfall Nowcasting Using Computer Vision  
**Team Name:** Cloud Cast  

**Team Members:**
- Abdullokh Rakhimjanov – [220333@centralasian.uz](mailto:220333@centralasian.uz)
- Natalya Lyubushkina – [220321@centralasian.uz](mailto:220321@centralasian.uz)
- Shakhzod Safarov – [221519@centralasian.uz](mailto:221519@centralasian.uz)

**Mentor:** Ibragim Atadjanov, Professor, Engineering School  
**Repository:** [https://github.com/Natrix1708/Satellite-Based-Cloud-Observation-and-Rainfall-Nowcasting-Using-Computer-Vision.git](https://github.com/Natrix1708/Satellite-Based-Cloud-Observation-and-Rainfall-Nowcasting-Using-Computer-Vision.git)

---

## 2. Abstract

This proposal presents a computer vision system developed for short-term forecasting of atmospheric conditions over Tashkent using real-time satellite imagery. The system integrates visible (VIS), infrared (IR), and water vapor (WV) channels to estimate cloud coverage, precipitation probability, and wind conditions for a specific local area.  
It aims to deliver forecasts at 15-minute intervals, achieving at least 90% accuracy for precipitation and cloud classification. The processed output will be visualized through an interactive dashboard displaying satellite overlays and forecasted weather data.

---

## 3. Problem & Motivation

Accurate and timely weather forecasting remains a challenge in developing regions such as Tashkent, where limited ground-based infrastructure reduces reliability.  
Traditional NWP (Numerical Weather Prediction) models offer global coverage but low spatial resolution and delay.  
This project seeks to bridge that gap by leveraging **Meteosat satellite data** and deep learning for **localized short-term nowcasting**.

---

## 4. Related Work

- CNNs and ConvLSTMs have proven effective in detecting cloud motion and precipitation from multispectral satellite imagery.  
- Studies using data from GOES and Himawari satellites have shown strong short-term forecasting performance.  
- However, many rely on large-scale computing clusters.  
Our project focuses on **lightweight ConvLSTM architectures** trained on **open-access Meteosat data**, providing an accessible approach for regional weather prediction.

---

## 5. Data & Resources

- **Primary Data:** Meteosat SEVIRI imagery (VIS, IR, WV) via EUMETSAT & Copernicus APIs  
- **Supporting Data:** OpenWeatherMap API, Meteostat API  
- **Format:** GeoTIFF / NetCDF → image tensors  
- **Tools:** Python, TensorFlow, Keras, OpenCV, NumPy, Rasterio, Pandas  
- **Hardware:** Google Colab GPU / local GPU-enabled workstation

---

## 6. Methodology

1. **Data Acquisition:** Retrieve Meteosat SEVIRI imagery every 15 minutes.  
2. **Preprocessing:** Crop to Tashkent region, normalize, align channels.  
3. **Labeling:** Pair frames with weather labels (rain, wind, clouds).  
4. **Model:** CNN + ConvLSTM for spatiotemporal prediction.  
5. **Training:** Supervised learning with Adam optimizer.  
6. **Visualization:** Streamlit dashboard for real-time forecast display.

---

## 7. Experiments & Evaluation

**Metrics:**
- Accuracy & F1-score (precipitation classification)  
- RMSE (wind & cloud estimation)  
- Inference latency (seconds/frame)

**Targets:**
- ≥90% accuracy  
- ≤1-minute latency

---

## 8. Risks & Mitigation

| Risk | Mitigation |
|------|-------------|
| Data gaps or API limits | Cache data locally; use multiple endpoints |
| Cloud occlusion/noise | Apply temporal smoothing and denoising |
| Hardware constraints | Use pre-trained CNN backbones |
| Low model accuracy | Adjust architectures and hyperparameters |

---

## 9. Timeline & Roles

| Weeks | Task | Responsible |
|-------|------|--------------|
| 1–2 | Data collection & preprocessing | Abdullokh Rakhimjanov |
| 3–4 | Model architecture & training | Shakhzod Safarov |
| 5–6 | Evaluation & optimization | Abdullokh Rakhimjanov |
| 7 | Dashboard integration & testing | Natalya Lyubushkina |

---

## 10. Expected Outcomes

- CNN + ConvLSTM model for localized weather nowcasting  
- Streamlit dashboard for live visualization  
- Validation of regional nowcasting feasibility with open data  

---

## 11. Ethical Considerations

This project uses only publicly available data and complies with all EUMETSAT and Copernicus usage policies.  
No human or animal data involved. All results are for educational, non-commercial purposes.

---

## 12. References

1. Moreira, N. de A. et al. (2022). *ConvLSTM for Weather Prediction using Radar and Satellite Images.*  
2. Lu, M. et al. (2023). *Spatiotemporal Prediction of Radar Echoes with ConvLSTM.*  
3. Fernández-Álvarez, J. C. et al. (2021). *Precipitation Nowcasting Using Satellite Data.*  
4. Liu, W. et al. (2022). *Rainfall Nowcasting via ConvLSTM Network.*  
5. Tan, C. et al. (2019). *FORECAST-CLSTM: A New Network for Cloudage Nowcasting.*  
6. Savale, V. et al. (2024). *Cloud Cover Segmentation and Motion Prediction.*  
7. Moran, S. et al. (2023). *Super-resolved Rainfall Prediction with Physics-Aware Deep Learning.*  
8. Tekin, S. F. et al. (2021). *Attention Mechanism on ConvLSTMs for Weather Forecasting.*

---

🛰️ *“Combining satellite data and deep learning for accessible, regional weather forecasting.”*
