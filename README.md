# AccessBox
Azure AKS node access box without public IPs.

## How to use

1. Deploy access box pod
`kubectl --kubeconfig k.yaml apply -f accessbox.yaml`

Make sure it is running:
`kubectl --kubeconfig k.yaml get po`

2. Exec into the pod
` kubectl --kubeconfig k.yaml exec accessbox -it -- /bin/bash `
