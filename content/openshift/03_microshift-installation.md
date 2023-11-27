# Installation de MicroShift (mode RPM)

## Téléchargement de l'image qcow2

Pour commencer, téléchargez l'image qcow2 de Red Hat Enterprise Linux depuis le lien suivant : 
https://access.redhat.com/downloads/content/479/ver=/rhel---9/9.3/x86_64/product-software


MicroShift est une plateforme légère et évolutive d'OpenShift, optimisée pour les déploiements locaux ou de développement. Ce guide vous explique comment l'installer sur Red Hat Enterprise Linux (RHEL).

## Procédure d'installation

### Activation des dépôts Red Hat de MicroShift
En tant qu'utilisateur root, exécutez la commande suivante pour activer les dépôts Red Hat de MicroShift :

```shell
sudo subscription-manager repos \
--enable rhocp-4.14-for-rhel-9-$(uname -i)-rpms \
--enable fast-datapath-for-rhel-9-$(uname -i)-rpms
```
Puis installez microshift

```shell
sudo dnf install -y microshift
```

###  Copie du pull secret vers /etc/crio

Téléchargez votre pull secret d'installation depuis la Console Cloud Hybride Red Hat (https://console.redhat.com/openshift/install/pull-secret) vers un dossier temporaire, par exemple, $HOME/openshift-pull-secret. 

Pour copier le pull secret dans le dossier /etc/crio de votre machine RHEL, exécutez :

```shell
sudo cp $HOME/openshift-pull-secret /etc/crio/openshift-pull-secret
```


