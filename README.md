### Créer le fichier manifeste de déploiement

#### Objectif : Rédiger un fichier manifeste Kubernetes pour déployer un serveur web NGINX basique dans votre namespace.
    Instructions :
        - Créez un fichier nommé nginx-deployment.yaml qui définit une ressource Deployment pour NGINX.
        - Définissez le nombre de replica à 3
        - Assurez-vous que le manifeste spécifie le namespace approprié, les labels, et les spécifications du conteneur.

### Créer le fichier manifeste de service

#### Objectif : Rédiger un fichier manifeste Kubernetes pour exposer le déploiement NGINX au sein du cluster.
    Instructions :
        - Créez un fichier nommé nginx-service.yaml qui définit une ressource Service pour exposer le déploiement NGINX.
        - Assurez-vous que le manifeste spécifie le namespace approprié, les sélecteurs, et les configurations de port.

### Déployer et vérifier

#### Objectif : Appliquer les manifestes pour déployer et vérifier l'application.
    Instructions :
        - Appliquez les manifestes de déploiement et de service en utilisant `kubectl apply -f <votre_fichier>`.
        - Appliquez le manifeste de mise à l'échelle pour ajuster le nombre de réplicas en utilisant `kubectl apply -f <votre_fichier>`.
        - Vérifiez les ressources dans votre namespace en utilisant `kubectl get all`.
*Optionnel*
        - Redirigez un port local vers le service pour accéder à l'application dans un navigateur web en utilisant `kubectl port-foward`.
        - Ouvrez un navigateur web et naviguez à http://localhost:8080 pour voir la page d'accueil NGINX.


### Pour lancer
#### Création Namespace
```shell
kubectl create namespace m2a-certiskills 
```
#### Création Deploiement 
```shell
kubectl --kubeconfig=m2a-certiskills-config.yml apply -f nginx-deployment.yaml
```
#### Création Service 
```shell
kubectl --kubeconfig=m2a-certiskills-config.yml apply -f nginx-service.yaml
```

#### Portfowarding (local)
récupération des noms
```shell
kubectl get pods -n m2a-certiskills
```

```shell
kubectl port-forward pod/pod/nginx-deployment-6dbc97b84b-4vpbj 8080:80 -n m2a-certiskills
```
