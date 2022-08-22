# If kibana is down what should we do ?

### Check volume

    docker volume ls

### Remove volume if kibana is down due to stroage full 
    
    docker volume rm kibana_elasticsearch-data

### Run kibana volume

    docker-compose up --volumes
    
### Execute  this command to run kibana

    docker-compose up -d
