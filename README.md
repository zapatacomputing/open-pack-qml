# z-qml

**Quantum Machine Learning docker images.**

## Info

* This image uses [qe-tools-base](https://github.com/zapatacomputing/qe-tools/blob/master/docker/qe-tools-base.Dockerfile) as the base image.
* Purpose is for installing QML libraries.
* Rigetti `qvm` and `quilc` (and [dependencies](http://docs.rigetti.com/en/stable/start.html)) are installed. More info [here](https://github.com/rigetti/qvm).

## Testing locally

Build the image:

```bash
docker build -t zapatacomputing/z-qml:nightly .
cd pele
docker build -t zapatacomputing/z-qml-pele:nightly .
```
If it finished without errors, your image is ready for production.

Check whether your images are there:

```bash
docker images
```

If you would like to inspect your docker container (i.e. go inside your container, inspect dir structure, run things, etc), you can run:

```bash
docker run -it zapatacomputing/z-qml:nightly bash
docker run -it zapatacomputing/z-qml-pele:nightly bash
```
