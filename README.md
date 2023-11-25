# General Tips for CKA
## Tips via YouTube
1. Define your shell alias 
```
alias k='kubectl'
alias kg='kubectl get'
alias kgp='kubectl get pods'
alias kns='kubens'
alias kcx='kubectx'
alias do='--dry-run=client -o yaml'
```
2. Enable kubectl autocompletion
```
Might be there by default, check cncf video
```
3. Use the shortnames for resources
```
NAME                              SHORTNAMES   APIVERSION                             NAMESPACED   KIND
componentstatuses                 cs           v1                                     false        ComponentStatus
configmaps                        cm           v1                                     true         ConfigMap
endpoints                         ep           v1                                     true         Endpoints
events                            ev           v1                                     true         Event
limitranges                       limits       v1                                     true         LimitRange
namespaces                        ns           v1                                     false        Namespace
nodes                             no           v1                                     false        Node
persistentvolumeclaims            pvc          v1                                     true         PersistentVolumeClaim
persistentvolumes                 pv           v1                                     false        PersistentVolume
pods                              po           v1                                     true         Pod
replicationcontrollers            rc           v1                                     true         ReplicationController
resourcequotas                    quota        v1                                     true         ResourceQuota
serviceaccounts                   sa           v1                                     true         ServiceAccount
services                          svc          v1                                     true         Service
customresourcedefinitions         crd,crds     apiextensions.k8s.io/v1                false        CustomResourceDefinition
daemonsets                        ds           apps/v1                                true         DaemonSet
deployments                       deploy       apps/v1                                true         Deployment
replicasets                       rs           apps/v1                                true         ReplicaSet
statefulsets                      sts          apps/v1                                true         StatefulSet
horizontalpodautoscalers          hpa          autoscaling/v1                         true         HorizontalPodAutoscaler
cronjobs                          cj           batch/v1                               true         CronJob
certificatesigningrequests        csr          certificates.k8s.io/v1                 false        CertificateSigningRequest
events                            ev           events.k8s.io/v1                       true         Event
ingresses                         ing          networking.k8s.io/v1                   true         Ingress
networkpolicies                   netpol       networking.k8s.io/v1                   true         NetworkPolicy
poddisruptionbudgets              pdb          policy/v1                              true         PodDisruptionBudget
podsecuritypolicies               psp          policy/v1beta1                         false        PodSecurityPolicy
priorityclasses                   pc           scheduling.k8s.io/v1                   false        PriorityClass
storageclasses                    sc           storage.k8s.io/v1                      false        StorageClass
```
4. Use dry-run to generate the yaml you need (i.e. from imparative to declarative). See alias' above.
5. Delete pods without waiting
```
export now='--force --grace-period 0'
k delete po nginx $now
```
6. Use kubectl -h to show some examples of how to run commands.
7. Use kubectl explain to show the definition of a resource (avoid the online docs)
```
k explain pod.spec
k explain pod.spec.containers
```
8. Create a temp pod for testing
```
k run -it busybox --rm --image=busybox -- sh
```
9. Bookmark freq used kubernetes resources
10. Practice, practice, practice
