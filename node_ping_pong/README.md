1. Build the Docker image:
$ docker build -t slim_ping_pong .
 
2. Run the Docker container:
$ docker run --name slim_ping_pong_container -p 3000:3000 -d slim_ping_pong
 
3. To test the ping/pong functionality:
$ curl http://localhost:3000/ping
