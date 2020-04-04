You could technically delete any K8 resources using `kubectl` but its not advisable here as the Tiller history will not remain synchronised.

List out all the hel creates releases by

```sh
helm ls
```

Then delete them using:

```sh
helm delete <name>
```

If you go to the configmaps in `kube-system` namespace, you will see some data regarding your release:

```sh
kubectl get configmaps --namespace=kube-system
```

So to delete that too you can use:

```sh
helm delete <name> --purge
```

For example:

```sh
$ helm ls                                                                                                                                                                     NAME            REVISION        UPDATED                         STATUS          CHART                   APP VERSION     NAMESPACE
gaudy-pika      1               Sat Apr  4 15:29:21 2020        DEPLOYED        nginx-demo-0.1.0        1.0             default
$ helm delete gaudy-pika                                                                                                                                                       release "gaudy-pika" deleted
$ kubectl get configmaps --namespace=kube-system                                                                                                      NAME                                 DATA   AGE
coredns                              1      47d
extension-apiserver-authentication   6      47d
gaudy-pika.v1                        1      29s
kube-proxy                           2      47d
kubeadm-config                       2      47d
kubelet-config-1.15                  1      47d
$ helm delete gaudy-pika --purge                                                                                                                                              release "gaudy-pika" deleted
```

If you want to delete tiller pod and deployment, you could do:

```sh
helm reset
```

But helm reset only deletes the server side. The local helm directory is preserved which is in your home folder:

For windows - C:\Users\<user>\.helm\

You can delete this too if you want to clean everything and also delete the binary.
