# try-concourse

First try ... https://github.com/concourse/concourse-docker

# Set up

    docker-compose up -d
    
Visit http://localhost:8080/ , download fly and install
    
    mv ~/Downloads/fly /usr/local/bin/fly
    chmod +x
    fly -version
    
    fly -t try login -c http://localhost:8080

Visit the link and enter username / password = test / test

# Run

## Execute single task

    cd try/basic
    fly -t try execute -c hello.yml     

## Execute pipeline

    cd try/basic
    fly -t try set-pipeline -n -c pipeline.yml -p my-pipeline
    fly -t try unpause-pipeline -p my-pipeline

Start job at http://localhost:8080/teams/main/pipelines/my-pipeline
       
# Further information

See your local concourse login context

    cat ~/.flyrc    

# Thanks

https://concourse-ci.org/
https://concoursetutorial.com/basics/task-hello-world/