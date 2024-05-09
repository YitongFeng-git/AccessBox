# AccessBox
Azure AKS node access box without public IPs.

## How to use

### Run AccessBox Pod

1. Deploy access box pod
`kubectl --kubeconfig k.yaml apply -f accessbox.yaml`

2. Make sure it is running:
`kubectl --kubeconfig k.yaml get po`

### Credential

1. Go to Azure dashboard -> VMSS -> Instance -> Connect -> SSH -> Click step3 "Replace/reset your SSH private key". Save the private key as key.pem

2. Go back to Azure dashboard -> VMSS -> Instance, click "Upgrade", copy "Private IP address"

### Access

1. Exec into the pod
` kubectl --kubeconfig k.yaml exec accessbox -it -- /bin/bash `

2. Paste the private key key.pem got from step "Credential"
`vi key.pem`

3. `chmod 400 key.pem`

4. SSH to the node
`ssh -i key.pem azureuser@<Private IP address>`
