## Build alpine image

```
docker build --tag cfs-bundle:alpine --file ./docker-dir/alpine/Dockerfile ./
```

## Run alpine image
```
docker run --mount src=$(pwd),dst=/${PWD##*/},type=bind --env CFS_COMPONENT=${PWD##*/} -it --rm cfs-bundle:alpine
```

then

```
cd cFS
make prep
make
make install
./cfs-test.sh
```

This currently breaks at the make step ~50%


## Build gcc image

```
docker build --tag cfs-bundle:gcc --file ./docker-dir/gcc-based/Dockerfile ./
```

## Run gcc image
```
docker run --mount src=$(pwd),dst=/${PWD##*/},type=bind --env CFS_COMPONENT=${PWD##*/} -it --rm cfs-bundle:gcc
```
then

```
cd cFS
make prep
make
make install
./cfs-test.sh
```
