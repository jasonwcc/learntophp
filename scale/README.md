# Use it with k8s or openshift
oc new-app --name scale1 --as-deployment-config php:7.3~https://github.com/jasonwcc/learntophp --context-dir scale 

oc logs -f bc/scale1

oc get pods

oc expose svc scale1

oc get route
<route-hostname>

curl <route-hostname>

# If use on non-k8s / non-ocp environment, you will get error on index
dnf -y install php

git clone https://github.com/jasonwcc/learntophp

cd learntophp/scale

php index.php
## error saying index not found, as the index meant to reveal which pod on cluster it ran
## nevertheless the script continue to show IP and version of the host
