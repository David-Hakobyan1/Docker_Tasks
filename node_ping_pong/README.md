1. Build the Docker image:
$ docker build -t node_ping_pong .
 
2. Run the Docker container:
$ docker run -p 3000:3000 -d node_ping_pong

3. To test the ping/pong functionality:
$ curl http://localhost:3000/ping
