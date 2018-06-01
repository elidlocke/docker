### First build the parent dockerfile:
docker build -t ft-rails:on-build .

### Then go into the child folder and build:
docker build -t app .

## Run the rails app:
docker run -ti --rm app
