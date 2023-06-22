# AI-Project

- Jianglong He: jh8011@nyu.edu (AWS contact person)
- Yiming Li: yl7538@nyu.edu
- Azraf Anwar: aa8542@nyu.edu


## Image Search

Please read the notebook [image_search_team6_final.ipynb](/image_search_team6_final.ipynb), you have access to it directly from Google Colab [here](https://colab.research.google.com/drive/1A-7Uj6YJ3uhPiGgOTz1nD2r2EdS10M4p?usp=sharing). It's a comprehensive notebook with everything required for the image search job.

## Video Search 

Please read the notebook [youtube_faces.ipynb](/youtube_faces.ipynb), you have access to it directly from Google Colab [here](https://drive.google.com/file/d/11L_2l6PmwSDR57qiSmEEaSL3eaeKz1V2/view?usp=sharing). Since embedding many videos into colab is not feasible, we went a head with showing the first frame of video to represent the video. We mannually picked 10 query videos and show the top 20 retrieval result of each queries. I have shown two set of results. First set is the result from the **(Use Average of Frame Embedding as Video Embedding Approach)** and 2nd set is te result of **(Pick Best Frame to Represent The Video Embedding Approach)**. Both set of results should be visible in the colab notebook under the **/Conclusion/Baseline Result** and **/Conclusion/Use Best Frame as Video Representation**.

<br>

We also stored the results in **[/images](/images)** folder. The **[/images/baseline_plots](/images/baseline_plots)** folder contains result for **(Use Average of Frame Embedding as Video Embedding Approach)** and **[images/best_frame_plots](/images/best_frame_plots)** folder contains result for **(Pick Best Frame to Represent The Video Embedding Approach)**. 

- each query image are named using this convention: **QueryIndex-{index}_Label-{person name}_Num_Simlar_Videos-{number similar videos in dataset}_AP-{average precision score of the query results}.jpg**
- each retreived images are named using this convention: **Rank-{rank#}_Label-{person name}_Dist-{euclidean distance score}_Match-{same label as query image or not}.jpg**

## Other Notebooks

We created some other notebooks in the process of writing the final one. They can show you our work in different stages, but please DO NOT consider them as final results. 

## Benchmark
- mAP1 = mAP of best 20 queries
- mAP2 = mAP of whole dataset as queries and retrieve and ranking top 20 neighbors
- mAP3 = mAP of whole dataset as queries and retrieve and ranking all neighbors

<br>

Pipeline | mAP1 | mAP2 | mAP3 
--- | --- | --- | ---
**FaceNet + Average Frame Embeddings for Video Embedding** | **1.0** |  **0.825**| **0.921**
**FaceNet + Pick Best Frame as Video Embedding** | 0.954 |  0.767| 0.896
**FaceNet + MLP Contrastive Learning** | 0.887 |  0.582| 0.804
**FaceNet + RNN Learn to Aggregator Frame Embeddings** |  0.906 |  0.603| 0.825
