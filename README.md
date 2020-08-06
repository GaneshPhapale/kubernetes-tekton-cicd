# This is CICD of simple hello app for tekton pipelines on kubernets or on openshift container platform 4.x.

# Prerequisite

 1. As you need tekton is install on your kubernetes/openshift enviornment.
    To setup it on kubernetes, follow: https://github.com/tektoncd/pipeline/blob/master/docs/install.md
  
 2. As we use dockerhub for image registery you need to login into the docker using command:
  
  $ docker login
  
  The docker login command will store the credential in default configuration file /root/.docker/config.json
  
 3. Also you need to create secret for pull reference in case of your private dockerhub registery. To crreate it use:
  $ kubectl create secret generic <your-secret-name> \
    --from-file=.dockerconfigjson=<path/to/.docker/config.json> \
    --type=kubernetes.io/dockerconfigjson
    
    NOTE: You need to replace your given secret name in pipeline service account in "service-account.yaml" file.
    Here  --from-file option is path to docker configuration file. The default path is: /root/.docker/config.json
    
    
    
# Executing Pipleine
  
  To exceute, create pipelineresource, task, pipleine, piplinerun using kubectl create -f command respectively.
  Wait for the pipeline to be fully executed.
