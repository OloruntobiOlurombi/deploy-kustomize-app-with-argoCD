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


You can manage your Argo CD installations either from the Web Interface or using the Command Line.


Using ArgoCD CLI
Step 1
Apart from the UI, ArgoCD also has a CLI. We have installed already the cli for you and authenticated against the instance.

Try the following commands

argocd app list
argocd app get kustomize-gitops-example
argocd app history kustomize-gitops-example
Let's delete the application and deploy it again but from the CLI this time.

First delete the app

argocd app delete kustomize-gitops-example
Confirm the deletion by answering yes in the terminal. The application will disappear from the Argo CD dashboard after some minutes.

Now deploy it again.

```
argocd app create demo \
--project default \
--repo https://github.com/codefresh-contrib/gitops-certification-examples \
--path ./kustomize-app/overlays/staging \
--sync-policy auto \
--dest-namespace default \
--dest-server https://kubernetes.default.svc
```
The application will appear in the ArgoCD dashboard.

Confirm the deployment

kubectl get all
Finish
If you've confirmed the deployment, click Check to finish this track.

