
#
# TASK:  
##  You want to deploy a busybox pod in default namespace. The name of the pod will come from the values.yaml file     
##  Write out ./values.yaml and ./templates/pod.yaml files 
##  AND the command to deploy the pod
##
## ANSWER:
##

### 
###  values.yaml
###
###  podName: foo
###
###

###
### templates\pod.yaml
### 
### apiVersion: v1
### kind: Pod
### metadata:
###   name: {{ .Values.podName }}
###   namespace: default
### spec:
###   containers:
###   - image: busybox
###     command:
###       - sleep
###       - "3600"
###     imagePullPolicy: IfNotPresent
###     name: {{ .Values.podName }}
###   restartPolicy: Always
### 

###
### Command to deploy:
###
###   helm install foo-helm . -f ./values.yaml
###

