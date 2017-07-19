Docker: [![](https://images.microbadger.com/badges/image/thomasnordquist/photon-geocoder.svg)](https://microbadger.com/images/thomasnordquist/photon-geocoder "Get your own image badge on microbadger.com") [![Docker Pulls](https://img.shields.io/docker/pulls/thomasnordquist/photon-geocoder.svg)](https://hub.docker.com/r/thomasnordquist/photon-geocoder/) [![](https://images.microbadger.com/badges/version/thomasnordquist/photon-geocoder.svg)](https://microbadger.com/images/thomasnordquist/photon-geocoder "Get your own version badge on microbadger.com")

Github:
[![GitHub issues](https://img.shields.io/github/issues/thomasnordquist/photon-docker.svg)](https://github.com/thomasnordquist/photon-docker/issues) [![GitHub stars](https://img.shields.io/github/stars/thomasnordquist/photon-docker.svg)](https://github.com/thomasnordquist/photon-docker/stargazers) [![GitHub forks](https://img.shields.io/github/forks/thomasnordquist/photon-docker.svg)](https://github.com/thomasnordquist/photon-docker/network)

Have your own geocoder up and running within the hour, you will require about 60GB of disk space and has no further dependencies.

Feel free to fork and improve.


# Run

The image itself is pretty small, the first time the container is executed, a 30GB searchindex will be downloaded.
The data volume is exposed as `/photon/photon_data` and can be mounted, this way you'll only have to download the data once.

## With `docker run`

```bash
docker run -p 2322:2322 -it thomasnordquist/photon-geocoder:latest
```

## Search

```
http://localhost:2322/api?q=berlin
```
*For more details on the API check the photon [github repository](https://github.com/komoot/photon).*



## Build from git
https://github.com/thomasnordquist/photon-docker

### With docker-compose
```bash
docker-compose build #optional
docker-compose up
```
*Note: if you abort the download, you have to remove the volume `photon_data` before restarting the container*


### With `docker build`
```bash
docker build --tag thomasnordquist/photon-geocoder .
```


## FAQ

 - How do I pass arguments to the `photon.jar` ?

   *The entrypoint accepts arguments for the `photon.jar`, you can invoke it by using `docker exec`*
 - Do I need to have nominatim ?

   *The container downloads the latest prebuilt search index, there is no immediate need to have nominatim installed.*

 - What is photon ?
  
   *photon is a geocoder, check out [their website](https://photon.komoot.de/) and their [github repository](https://github.com/komoot/photon)*
