# Simple Python app Tryout
https://jenkins.io/doc/tutorials/build-a-python-app-with-pyinstaller

## Jenkins is run from Docker Container (the image is prebuild):
`docker run \
  --rm \
  -u root \
  -p 8080:8080 \
  -v jenkins-data:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v "$HOME":/home \
  jenkinsci/blueocean`

See if container exists with docker ps.
Enter container with docker exec -it <container name> bash (or /bin/bash, do not know the difference as of now)

## Build pipeline
Code is stored in git (this tutorial locally). Pipeline -> from SCM -> Git -> path to folder on drive.
TODO: try that with git

Blue Ocean is used to run the pipeline (it visualises the prozess).

Create Jenkinsfile. In this tutorial there is 1 agent per CI-stage, e.g. the python container from Build is stopped when moving on to the next stage (lifespan == stage time).

## On Windows
"%HOMEPATH%" not recognised as valid path...write directory explicit.
