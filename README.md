# mkvdts2ac3-docker

This is a docker image for running script [mkvdts2ac3](https://github.com/JakeWharton/mkvdts2ac3). 

Which based on [sameersbn/ffmpeg](https://hub.docker.com/r/sameersbn/ffmpeg/) as base image with following tools:
  * [ffmpeg](http://ffmpeg.org/) - Audio conversion tool
  * [mkvtoolnix](http://www.bunkus.org/videotools/mkvtoolnix/) - Matroska tools
  * [rsync](http://rsync.samba.org/) - File transfer and synchronization

## Usage

Suppose you have a /path/to/film.mkv file with DTS format audio track.

### pull the image

```bash
$ docker pull hialan/mkvdts2ac3
```

### change path to the directory which contain film.mkv 

```bash
$ cd "/path/to"
```

### create a working tmp dir

```bash
$ mkdir /path/to/tmp
```

### run the script

```bash 
$ docker run -it --rm=true -v "`pwd`":/data hialan/mkvdts2ac3 \
	-w /data/tmp -n /data/film.mkv
```

The image export the mount point /data, so we mount current path to /data, and all the path should use relative path to /data. 


