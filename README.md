# deploy-kustomize-app-with-argoCD


Using the ArgoCD GUI
We installed Argo CD for you and you can login in the UI tab.

The UI starts empty because nothing is deployed on our cluster. Click the "NEW APP" button on the top left and fill the following details:

application name : kustomize-gitops-example

project: default

sync policy: automatic

repository URL: https://github.com/codefresh-contrib/gitops-certification-examples

path: ./kustomize-app/overlays/staging

Cluster: https://kubernetes.default.svc (this is the same cluster where ArgoCD is installed)

Namespace: default

Leave all the other values empty or with default selections. Finally click the Create button. The application entry will appear in the main dashboard. Click on it.

Congratulations! Your have setup your first Kustomize application with GitOps.

You should see the following.synced app

Wait some time for the application to start up and then visit the "Deployed App" to see it running. You will see that it has loaded the staging value for the database.
