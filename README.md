##Command
$ docker run -it --rm -v /app/node_modules -p 3001:3000 -e CHOKIDAR_USEPOLLING=true react-docker:dev
     
##Description
**-it** starts the container in interactive mode.

**--rm** removes the container and volumes after the container exits.
-v ${PWD}:/app mounts the code into the container at “/app”.

**Since we want to use the container version of the “node_modules” folder, we configured another volume: -v /app/node_modules.**

**-p** 3001:3000 exposes port 3000 to other Docker containers on the same network (for inter-container communication) and port 3001 to the host.

**-e CHOKIDAR_USEPOLLING=true** enables a polling mechanism via chokidar (which wraps fs.watch, fs.watchFile, and fsevents) so that hot-reloading will work.