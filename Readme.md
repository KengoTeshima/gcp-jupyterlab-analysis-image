# jupyterlab-analysis-image
- jupyter lab docker image for analysis 
- This docker image is intended for use with ai platform notebook on google cloud platform.
- If you want to run it local, follow [here](https://cloud.google.com/ai-platform/deep-learning-containers/docs/getting-started-local)

## Docker image


### base image
`gcr.io/deeplearning-platform-release/base-cpu`

### add content
- python librarygcl
- jupyterlab extension

### build
Please install the following in advance
- [gcloud](https://cloud.google.com/sdk/docs/install) or [cloud shell](https://console.cloud.google.com/?cloudshell=true&_ga=2.71680787.1264506767.1618149083-13444314.1612355846&_gac=1.217834980.1618150645.CjwKCAjwvMqDBhB8EiwA2iSmPEHcLPNvw8zm2hEr8rAcE4qM0pTB0FewJByO2FjjsPQ5ZJhBndgBFxoC2GsQAvD_BwE)
- [docker](https://docs.docker.com/get-docker/)

```sh
$ git clone --recursive git@github.com:KengoTeshima/jupyterlab-analysis-image.git
$ cd jupyterlab-analysis-image
$ docker build -t gcr.io/[project_name]/jupyterlab-analysis-image:latest .
```

### push image

```sh
# auth
$ gcloud auth login
$ gcloud auth configure-docker 

# push
$ docker push gcr.io/[project_name]/jupyterlab-analysis-image:latest
```

## usage
1. [GCP AI Platform Notebooks](https://console.cloud.google.com/ai-platform/notebooks) > new instance > Customize instance
2. environment > Custom Container
3. Docker Container image `gcr.io/[project_name]/jupyterlab-analysis-image:latest` 
4. Create
