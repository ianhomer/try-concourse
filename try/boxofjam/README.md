Set pipeline

    fly -t try set-pipeline -n -c pipeline.yml -p boxofjam

Clear cache

    fly -t try clear-task-cache -j boxofjam/job-build -s build-npm -c resource-boxofjam/node_modules