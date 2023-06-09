# DeployingAscalableAppWithKubernetesOnGCP

Cloud Computing projects #GCP

GCP
open the cloud shell
upload the app zip file
ls
to check if succesfull
unzip name.zip

unzip the file

cd tcb-vote

gcloud config set project <projectid>

fromt the docs, set the app
authorize

gcloud services enable cloudbuild.googleapis.com --project <projectid>

enable cloud API

gcloud builds submit --tag gcr.io/<projectID>/tcb-vote-front

create docker image

open the container registery

you can see the tcb.vote app

create kubernetes cluster on the portal
choose autopilot , configure
then create

after the cluster is ready

project id changes, so we copy the new to update in the Yaml file

container images

click on the cluster ,
connect
the copy the credentials
and paste in the shell to authenicate
something like this down below

gcloud container get-credentials kubernetes-cluster-1

kubectl get nodes

kubectl apply -f tcb-vote-plus-radis-v2-yaml

deploy the app with the name of the app file

kubectl get pods

kubectl get deployment tcb-vote-front

kubectl autoscale deployment tcb-vote-front --cpu-percent=50 --min=1 --max=10

autoscalling conditions min,max pods on horizontal autoscale

kubecktl get hpa

kubectl run -i --tty load-generator -rm --image=busybox:1.28 --restart=No ver -- /bin/sh -c "while sleep 0.01; do wget -q -0- http://tcb-vote-front;done\*

increase the load
