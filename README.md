# implantar-um-cluster-do-AKS-Servi-o-de-Kubernetes-do-Azure-usando-a-CLI-do-Azure

Dans cet article
Avant de commencer
Créer un groupe de ressources
Créer un cluster AKSCreate an AKS cluster
Se connecter au cluster

az group create --name myResourceGroup --location eastus

az aks create --resource-group myResourceGroup --name myAKSCluster --enable-managed-identity --node-count 1 --generate-ssh-keys
az aks get-credentials --resource-group myResourceGroup --name myAKSCluster
kubectl get nodes
kubectl apply -f aks-store-quickstart.yaml
kubectl get pods
kubectl get service store-front --watch

Supprimer le cluster
Si vous n’avez pas l’intention de suivre le didacticiel AKS, nettoyez les ressources inutiles pour éviter les frais Azure. Appelez la commande az group delete pour supprimer le groupe de ressources, le service de conteneur et toutes les ressources associées.

az group delete --name myResourceGroup --yes --no-wait
