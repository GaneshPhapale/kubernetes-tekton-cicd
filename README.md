# tekton-cicd

# This is CICD of simple hello app for tekton pipelines on kubernets or on openshift container platform.

# 1. Prerequisite

  # As you need tekton in install on your kubernetes/openshift enviornment.
  
  As we use dockerhub for image registery you need to login into the docker using command:
  
  # $ docker login
  
  The docker login command will store the credential in default configuration file /root/.docker/config.json
  
  Also you need to create secret for pull reference in case of your private dockerhub registery. To crreate it use:
  # kubectl create secret generic <your-secret-name> \
    --from-file=.dockerconfigjson=<path/to/.docker/config.json> \
    --type=kubernetes.io/dockerconfigjson
    
    Here # --from-file option is path to docker configuration file. The default path is:
    # /root/.docker/config.json
    
    
    
# 2. Executing Pipleine
  
  To exceute, create pipelineresource, task, pipleine, piplinerun respectively.
  Wait for the pipeline to be fully executed.
