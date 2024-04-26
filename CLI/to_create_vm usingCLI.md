
## Start with creating a Resource Group
az group create --name learn-azure-cli --location eastus

## Set the Resource Group as default (Optional)

az config set defaults.group=learn-azure-cli




## Create VM with Vnet


az vm create --resource-group learn-azure-cli --name vmName --image Ubuntu2204 --vnet-name default --subnet default --generate-ssh-keys --output json --verbose

## above command gives below output

PS C:\Users\ragha> az vm create --resource-group learn-azure-cli --name vmName --image Ubuntu2204 --vnet-name default --subnet default --generate-ssh-keys --output json --verbose
Configured default 'learn-azure-cli' for arg resource_group_name
SSH key files 'C:\Users\ragha\.ssh\id_rsa' and 'C:\Users\ragha\.ssh\id_rsa.pub' have been generated under ~/.ssh to allow SSH access to the VM. If using machines without permanent storage, back up your keys to a safe location.
{
  "fqdns": "",
  "id": "/subscriptions/a3903bf5-dd68-419c-81dd-c2fa24248ee7/resourceGroups/learn-azure-cli/providers/Microsoft.Compute/virtualMachines/vmName",
  "location": "eastus",
  "macAddress": "60-45-BD-D3-83-ED",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "13.92.209.105",
  "resourceGroup": "learn-azure-cli",
  "zones": ""
}
Command ran in 47.902 seconds (init: 0.366, invoke: 47.537)



## Delete the Resource Group to delete all the resources




az group delete --name learn-azure-cli