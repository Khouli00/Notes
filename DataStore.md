#DataStore

The PowerCLI Datastore Provider (VimDatastore) works with the PowerShell drive functionality to expose access to files and directories on vSphere datastores. You can use the default vmstore: or vmstores: inventory drives, or create custom drives with the New-PSDrive commandlet. Files and directories can be copied using the Copy-DatastoreItem commandlet. For more information, see the The Datastore Provider section of the vSphere PowerCLI Administration Guide.

To create a new custom PowerShell drive for a vSphere datastore:
1.Connect to an ESX/ESXi host or vCenter Server using PowerCLI:

````PowerCli
Connect-VIServer -Server ServerNameOrIPAddress
````

2.Get a datastore object:

$datastore = Get-Datastore "MyDatastoreName"


3.Create a new PowerShell drive, such as ds:, that maps to $datastore:

New-PSDrive -Location $datastore -Name ds -PSProvider VimDatastore -Root "\"
