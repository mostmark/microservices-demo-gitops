# Microservices Demo Application Gitops

Login to the openshift cluster as cluster-admin

To deploy OpenShift GitOps:

        git clone https://github.com/mostmark/microservices-demo-gitops
        cd microservices-demo-gitops
        oc apply -k deploy/argocd

Watch the pods starting up in the openshift-gitops project. Wait to proceed until all are available.

        watch oc get pods -n openshift-gitops

Get the route to ArgoCD using the following command:

        oc get route openshift-gitops-server -n openshift-gitops --template='https://{{.spec.host}}'

## Deploy the Microservies Demo Application

        oc apply -k deploy/application/microservices-demo-dev
