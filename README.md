# 📺 YouTube Trending Videos EDA

> **Exploratory Data Analysis of YouTube Trending Videos in India using Python, NumPy, Pandas, and Matplotlib.**

---

## 📌 Project Overview

This project analyzes **YouTube trending videos in India** to understand what type of content gains visibility, which channels appear most frequently, how videos perform in terms of views and engagement, and whether publishing patterns influence trending activity.

The analysis was performed using **NumPy, Pandas, and Matplotlib**, following a structured Exploratory Data Analysis approach.

The project focuses on converting raw YouTube data into **clear, data-driven business insights** that can help content creators, media companies, and digital marketing teams better understand audience behavior.

---

## 🎯 Project Objectives

* Analyze the distribution of trending videos across categories.
* Identify channels that frequently appear in the trending list.
* Identify the most viewed trending videos.
* Analyze the relationship between views and audience engagement.
* Identify temporal patterns in trending activity.
* Understand characteristics of highly viewed videos.
* Generate practical business recommendations from the analysis.

---

## 📊 Dataset

**Dataset:** Trending YouTube Video Statistics

**Source:** Kaggle — `datasnaek/youtube-new`

**Country:** India

**File Used:** `INvideos.csv`

The dataset contains information about YouTube videos that appeared on the trending list, including:

* Video ID
* Trending Date
* Video Title
* Channel
* Category
* Publishing Time
* Views
* Likes
* Dislikes
* Comments
* Tags
* Video Status
* Description

🔗 **Dataset:**
https://www.kaggle.com/datasets/datasnaek/youtube-new

---

## 🛠️ Tools & Technologies

* **Python**
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Kaggle Notebook**
* **GitHub**

> **Note:** This project intentionally uses only NumPy, Pandas, and Matplotlib for the EDA workflow.

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Data Transformation
   ↓
Exploratory Data Analysis
   ↓
Visualization
   ↓
Business Insights
   ↓
Recommendations
   ↓
Conclusion
```

---

## 🧹 Data Cleaning & Preparation

The dataset was examined and prepared before performing the analysis.

### Cleaning Steps

* Checked dataset structure and data types.
* Identified missing values.
* Removed **4,263 exact duplicate records**.
* Checked numerical columns for invalid values.
* Converted date and time columns into appropriate datetime formats.
* Created additional time-based features.
* Mapped numerical category IDs to meaningful category names.
* Retained repeated video IDs because the same video can appear in the trending list on multiple dates.
* Retained **561 missing descriptions** because the description column was not required for the analysis.

### Final Dataset

| Metric                    |      Value |
| ------------------------- | ---------: |
| Original Records          | **37,352** |
| Duplicate Records Removed |  **4,263** |
| Final Records             | **33,089** |
| Columns                   |     **23** |

---

# 📈 Exploratory Data Analysis

## Q1. Which video categories appear most frequently?

### Top Categories

| Category        | Trending Records |
| --------------- | ---------------: |
| Entertainment   |       **14,764** |
| News & Politics |        **4,709** |
| Music           |        **3,292** |
| Comedy          |        **2,967** |
| People & Blogs  |        **2,367** |

### 💡 Insight

**Entertainment** dominates the trending dataset with **14,764 records**, representing approximately **44.6%** of all cleaned records.

---

## Q2. Which YouTube channels have the highest number of trending records?

### Top Channels

| Rank | Channel            | Records |
| ---: | ------------------ | ------: |
|    1 | VikatanTV          | **208** |
|    2 | ETV Plus India     | **206** |
|    3 | SAB TV             | **206** |
|    4 | etvteluguindia     | **205** |
|    5 | Flowers Comedy     | **202** |
|    6 | Study IQ education | **202** |
|    7 | SET India          | **199** |
|    8 | Tarang TV          | **199** |
|    9 | Mazhavil Manorama  | **196** |
|   10 | RadaanMedia        | **193** |

### 💡 Insight

**VikatanTV** recorded the highest number of trending appearances with **208 records**.

The relatively small difference between the top channels indicates that trending visibility is distributed across several established channels.

---

## Q3. Which trending videos receive the highest number of views?

The highest recorded view count was:

> **125.43 Million Views**

The highest-viewed records were dominated by major entertainment releases, including:

* *YouTube Rewind: The Shape of 2017*
* *Marvel Studios' Avengers: Infinity War Official Trailer*

### 💡 Insight

All of the top 10 highest-viewed records belonged to the **Entertainment** category.

Because the dataset contains multiple trending records for the same video, these figures represent recorded view counts rather than unique-video performance.

---

## Q4. How does audience engagement relate to views?

Three engagement metrics were created:

```text
Like Rate       = Likes / Views × 100
Comment Rate    = Comments / Views × 100
Engagement Rate = (Likes + Comments) / Views × 100
```

### Engagement Results

| Metric          |   Average |
| --------------- | --------: |
| Like Rate       | **2.19%** |
| Comment Rate    | **0.26%** |
| Engagement Rate | **2.45%** |

### Correlation with Views

| Metric          | Correlation |
| --------------- | ----------: |
| Like Rate       |   **0.042** |
| Comment Rate    |  **-0.003** |
| Engagement Rate |   **0.035** |

### 💡 Insight

The correlation between **views and engagement rate is only 0.035**, indicating an extremely weak relationship.

This suggests that high reach does not necessarily mean proportionally high audience engagement.

---

## Q5. When are videos most likely to trend?

### Trending Records by Month

| Month    |   Records |
| -------- | --------: |
| December | **5,803** |
| January  | **5,418** |
| March    | **4,735** |
| February | **4,536** |
| May      | **4,057** |
| April    | **3,487** |
| November | **3,209** |
| June     | **1,844** |

### Trending Records by Publishing Day

| Day       |   Records |
| --------- | --------: |
| Friday    | **5,573** |
| Saturday  | **5,196** |
| Thursday  | **4,986** |
| Tuesday   | **4,619** |
| Monday    | **4,607** |
| Wednesday | **4,550** |
| Sunday    | **3,558** |

### 💡 Insight

**December** had the highest number of trending records with **5,803**, while **Friday** had the highest number of records by publishing day with **5,573**.

> **Note:** The dataset covers a limited time period, so these patterns should not be interpreted as universal YouTube publishing rules.

---

## Q6. What characteristics are common among highly viewed videos?

The **75th percentile of views** was used to classify highly viewed records.

### View Threshold

**732,022 views**

### Performance Comparison

| Metric           | Highly Viewed |       Other |
| ---------------- | ------------: | ----------: |
| Average Views    |     **3.29M** | **233.08K** |
| Average Likes    |    **88,325** |   **4,673** |
| Average Comments |     **8,375** |     **574** |
| Engagement Rate  |     **2.90%** |   **2.30%** |

### Top Categories Among Highly Viewed Records

| Category         |   Records |
| ---------------- | --------: |
| Entertainment    | **3,008** |
| Music            | **1,740** |
| Comedy           | **1,013** |
| Film & Animation |   **701** |
| News & Politics  |   **511** |

### 💡 Insight

Highly viewed records generated substantially greater reach and audience interaction.

However, their average engagement rate was only moderately higher than other records (**2.90% vs. 2.30%**), reinforcing that **views and engagement should be evaluated separately**.

---

# 💡 Key Business Insights

### 1️⃣ Entertainment dominates trending content

Entertainment represents approximately **44.6%** of the cleaned trending records.

### 2️⃣ Trending visibility is distributed

VikatanTV led the channel analysis with **208 trending records**, but the top channels had relatively similar performance.

### 3️⃣ Major entertainment releases can generate massive reach

The highest recorded video reached approximately **125.43 million views**.

### 4️⃣ Views do not guarantee engagement

The correlation between views and engagement rate was only **0.035**.

### 5️⃣ Timing shows noticeable patterns

December had the highest monthly activity, while Friday had the highest representation by publishing day.

### 6️⃣ Highly viewed content is strongly entertainment-focused

Entertainment accounted for **3,008 highly viewed records**, followed by Music and Comedy.

---

# 💼 Business Recommendations

* Focus on high-demand content categories such as **Entertainment, Music, and Comedy** when aligned with the target audience.
* Study successful major entertainment releases to understand content formats and audience reach.
* Evaluate content using both **views and engagement rate**, rather than relying on views alone.
* Test publishing schedules around high-performing periods such as Friday and Saturday.
* Analyze consistently successful channels to identify repeatable content strategies.
* Continuously monitor views, likes, comments, categories, and engagement to support data-driven content decisions.

---

# 📁 Project Structure

```text
youtube-trending-videos-eda/
│
├── README.md
│
└── youtube_trending_videos_eda.ipynb
```

---

# 📚 References

* **Kaggle Dataset:**
  https://www.kaggle.com/datasets/datasnaek/youtube-new

* **NumPy Documentation:**
  https://numpy.org/doc/

* **Pandas Documentation:**
  https://pandas.pydata.org/docs/

* **Matplotlib Documentation:**
  https://matplotlib.org/stable/

---

# 🧠 Skills Demonstrated

`Python` `NumPy` `Pandas` `Matplotlib` `Data Cleaning` `Data Transformation` `Exploratory Data Analysis` `Data Visualization` `Statistical Analysis` `Correlation Analysis` `Business Insights` `Data Storytelling`

---

# 👨‍💻 Author

## L Shubham

**Data Analyst | Power BI | SQL | Python | Excel | Tableau | Data Visualization | Business Intelligence**

🔗 **GitHub:**
https://github.com/shubham-lingam

🔗 **LinkedIn:**
https://www.linkedin.com/in/shubham-lingam

---

⭐ **If you found this project useful, consider giving the repository a star.**
