# YouTube Growth Predictor

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![ML](https://img.shields.io/badge/ML-GradientBoosting-green.svg)](https://scikit-learn.org/)
[![API](https://img.shields.io/badge/API-YouTube-red.svg)](https://developers.google.com/youtube/v3)

##  Project Description
ML system predicting YouTube video views and viral potential. Analyzes 900+ videos, extracts temporal/text/duration features, and provides actionable creator insights. Best model: Gradient Boosting (R²=0.7085).


##  Key Findings
- **Best Upload Time**: Saturday 5 PM (40% more views)
- **Optimal Duration**: 10-20 minutes
- **Top Feature**: Channel average views
- **Best Model**: Gradient Boosting (R² = 0.7085)

## Data Collection

### YouTube API Setup
1. Go to Google Cloud Console
2. Create new project
3. Enable YouTube Data API v3
4. Create API Key credentials
5. Copy your API key

### Channels Analyzed
- MrBeast
- Tanmay Bhat
- Technical Guruji
- Mrwhosetheboss

### Data Fields Collected
- video_id: Unique video identifier
- title: Video title
- description: Video description
- published_at: Upload date/time
- channel_name: Channel name
- tags: Video tags
- duration: Video length
- view_count: Total views
- like_count: Total likes
- comment_count: Total comments

### Data Collected
| Channel | Videos | Avg Views |
|---------|--------|-----------|
| MrBeast | 900+ | 72.9M |
| Tanmay Bhat | 900+ | 5.2M |
| Technical Guruji | 900+ | 598K |
| Mrwhosetheboss | 900+ | 11.4M |

## Feature Engineering

### Temporal Features
- publish_hour, publish_dayofweek, publish_month
- is_weekend, is_weekday
- is_saturday_5pm
- days_since_last_upload

### Duration Features
- duration_minutes
- duration_category
- is_short, is_long

### Channel Features
- channel_avg_views
- channel_avg_likes
- channel_upload_freq

### Target Variables
- views_7day (Regression)
- will_cross_100k (Classification)
- will_cross_1M (Classification)
- will_cross_10M (Classification)

## Models & Results

### Regression Models
| Model | R2 Score | RMSE |
|-------|----------|------|
| Gradient Boosting | 0.7085 | 66.7M | 
| Random Forest | 0.6623 | 71.8M |
| XGBoost | 0.6013 | 78.0M | 
| KNN | 0.6352 | 74.6M | 

### Classification Results
| Threshold | Best Model | Accuracy |
|-----------|------------|----------|
| 100K Views | Gradient Boosting | 0.85+ |
| 1M Views | Random Forest | 0.78+ |
| 10M Views | Random Forest | 0.92+ |

### Channel-Specific Performance
| Channel | R2 Score | MAE |
|---------|----------|-----|
| MrBeast | 0.5750 | 65.0M |
| Tanmay Bhat | 0.4595 | 876K |
| Mrwhosetheboss | -3.83 | 11.4M |
| Technical Guruji | -46.68 | 598K |

## SHAP Analysis Insights

### Top 5 Most Important Features
1. Channel Average Views
2. Day of Week (Saturday)
3. Hour of Day (5 PM)
4. Days Since Last Upload
5. Clickbait Score

### Feature Impact Ranking
Channel Avg Views - Highest Impact
Saturday Upload - 95% Impact
5 PM Upload - 88% Impact
Days Since Upload - 72% Impact
Clickbait Score - 65% Impact

## Creator Recommendations

### 1. Best Upload Time
Upload on Saturday at 5 PM
Videos get 40% more views on average

### 2. Optimal Duration
Keep videos between 10-20 minutes
Highest engagement and retention

### 3. Title Optimization
Use clickbait score between 0.4-0.6
Include 1-2 emojis
Use exclamation points sparingly
Keep title under 60 characters

### 4. Tags Strategy
Include 5-10 relevant tags
Use channel-specific keywords
Mix broad and niche tags

### 5. Consistency
Maintain regular upload schedule
2-3 days between uploads is optimal
Avoid long gaps (>7 days)

## Future Improvements

- Real-time prediction API
- Streamlit dashboard
- More channels (gaming, education, vlogs)
- Subscriber growth prediction
- A/B testing recommendations
- YouTube Shorts analysis


