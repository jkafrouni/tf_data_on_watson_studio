# Using tf.data to speed up Deep Learning training on Watson Studio
This repo contains sample code to build efficient data pipelines to train DL models on Watson Studio by leveraging tf.data.
These notebooks support a medium article I wrote in Nov 2021.

There are two examples:
- [Example 1](train-vgg16-download-cos-py38.ipynb) Training by downloading all the data to the notbook environment first
- [Example 2](train-vgg16-read-from-cos-py38.ipynb) Training by reading the data on the fly from Cloud Object Storage

The main idea is to leverage tf.data to prefetch and process data efficiently, directly from Cloud Object Storage, so that the data pipeline does not become the bottleneck. This is possible thanks to tf.data's integration with S3 and the fact that IBM Cloud Object Storage exposes the same API as S3. It could therefore easily be adapted to AWS S3, [MinIO](https://min.io/), or any other object storage that is S3 compatible...
