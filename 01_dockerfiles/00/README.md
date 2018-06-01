###To build the dockerfile into an image:
docker build -t elizabeth/alpine-vim .

###Make sure the image has been created:
docker image ls

###To run the new image:
docker run -ti --rm elizabeth/alpine-vim  
