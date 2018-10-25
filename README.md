The code shows how to use node.js runtime for cloud functions to invoke vision API for image recognition and synchronously add the results to BigQuery for real-time analysis.

1) Enable: Cloud Vision API.
2) BigQuery: Create a new dataset named images_dataset in BigQuery; Create a new table named image_info with these fields:
file as type string, description as type string, score as type float
3) Cloud Storage: Create a new Cloud Storage bucket if you don't have one
4) Cloud Functions: Edit YOUR_PROJECT_ID in index.js and set to your project ID.
5) Deploy: $ gcloud functions deploy analyzeImage --runtime nodejs8 --trigger-resource YOUR_BUCKET_NAME --trigger-event google.storage.object.finalize
