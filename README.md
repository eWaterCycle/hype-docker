# hype-docker
Docker file containing the Hydrological Predictions for the Environment (HYPE) model (http://hypecode.smhi.se/).
### Building the image
To build this docker image locally: install git and docker, clone this repo and within this repo directory type
```
docker build . -t hype-docker
```
to get an image named `hype-docker` on your local system.
### Using the image
This docker file assumes the HYPE model input to be in the folder /data within the container. Hence you need to mount your data directory when running the image:
```
docker run -v <HYPE_DATA>:/data hype-docker:latest
```
where `<HYPE_DATA>` contains your input data and the results folder that HYPE will write to. This folder must contain a file `filedir.txt` that should contain the single line
```
/data/
```
