# docker-agent

Docker agent recognizes following env variables:

```
    DOCKER_AGENT_BACKEND_URL                Address of 'container-storage' backend
    DOCKER_AGENT_BACKEND_PORT               Port of 'container-storage' backend
    DOCKER_AGENT_DUMMY_BACKEND              If true, then we don't connect to remote backend
    DOCKER_AGENT_SKIP_PACKETBEAT            If true, there will be no Packetbeat setup/monitoring
    DOCKER_AGENT_PACKETBEAT_IMAGE           Name of the Packetbeat image, default is 'pipetop/docker-agent-pb'
    DOCKER_AGENT_ELASTIC_SEARCH_ADDRESS     Elastic search address for Packetbeat to connect to (<host:port>)
    DOCKER_AGENT_LOGSTASH_ADDRESS           Logstash address for Packetbeat to connect to (<host:port>)
    DOCKER_AGENT_MONITOR_HTTP_PORTS         List of http ports that Packetbeat instances will capture
```

Example run command with dummy backend:

```
docker run -e DOCKER_AGENT_DUMMY_BACKEND=1 -e DOCKER_AGENT_ELASTIC_SEARCH_ADDRESS=192.168.99.100:9200 -v /var/run/docker.sock:/var/run/docker.sock docker_agent
```
