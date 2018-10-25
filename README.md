#### The code shows how to use Cloud Functions node.js runtime to invoke Cloud Vision API for image recognition and synchronously add the results to BigQuery for real-time analysis.
---
1) Enable the APIs inlcuidng Cloud Vision, BigQuery, Cloud Storage, Cloud Functions.
2) Create a new dataset named **images_dataset** in BigQuery; Create a new table named **image_info** with these fields:
**file** as type string, **description** as type string, **score** as type float
3) Create a Cloud Storage bucket if you don't have one
4) Replace **PROJECT_ID** in index.js with your project ID.
5) Replace **BUCKET_NAME** with your bucket name and deploy the Cloud Function
```
gcloud functions deploy analyzeImage --runtime nodejs8 --trigger-resource BUCKET_NAME --trigger-event google.storage.object.finalize
```
