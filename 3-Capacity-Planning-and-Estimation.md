![image](https://github.com/user-attachments/assets/7dac65dc-a582-4ea1-97da-71d8b4636b63)

### Capacity Planning and Estimation: How Much Data Does YouTube Store Daily?

To estimate how much data YouTube stores daily, we need to account for video uploads, supplementary data, transcoding, and caching.

### 1. **Video Uploads**

- **Assumptions**:
  - **500 hours of video are uploaded per minute** (as reported by YouTube).
  - **Average video size**: 100 MB per hour of video.
  
- **Calculation**:
  - **500 hours/minute** × **60 minutes/hour** = **30,000 hours/day**
  - **30,000 hours/day** × **100 MB/hour** = **3,000,000 MB/day** = **3,000 GB/day** = **3 TB/day**.

### 2. **Supplementary Data**

- In addition to video content, YouTube stores **metadata** (titles, descriptions, etc.), **user data** (accounts, preferences), and **backup data**.
- These require extra storage, but for simplicity, we assume it's **10-20%** of the video storage.

- **Estimation**:  
  - **3 TB/day** × **20%** = **0.6 TB/day** for supplementary data.

### 3. **Video Transcoding**

- After uploading, videos are processed into **multiple resolutions** (e.g., 360p, 720p, 1080p, 4K) for different devices.
- **Assumption**: Each video has **5 different versions**.
- **Calculation**: 
  - For **1 GB video**, 5 versions = **5 GB storage**.
  - With **500 hours of video uploaded per minute**, this would result in an additional storage requirement of:
    - **500 hours/minute** × **60 minutes/hour** = **30,000 hours/day**.
    - **30,000 hours/day** × **100 MB/hour** = **3,000,000 MB/day** = **3,000 GB/day** = **3 TB/day**.
    - **3 TB/day** × **5 versions** = **15 TB/day** for transcoding.

### 4. **Caching**

- YouTube uses **caching** to store frequently accessed videos closer to users, reducing server load and improving speed.
- Caching is dynamic and will vary by content popularity, but we can assume **a significant amount** of popular videos are cached in **distributed servers**.

### **Total Storage Estimate:**
- **Video uploads**: **3 TB/day**
- **Supplementary data**: **0.6 TB/day**
- **Transcoding**: **15 TB/day**
- **Total estimated storage**: **18.6 TB/day**

### Conclusion:
YouTube likely stores **around 18-20 TB of new data daily** considering uploads, supplementary data, transcoding, and caching. This is just an estimate and the actual amount could be higher due to more versions, additional data types, and caching.
