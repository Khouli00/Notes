#DataStore

More on KB => http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2001041

The PowerCLI Datastore Provider (VimDatastore) works with the PowerShell drive functionality to expose access to files and directories on vSphere datastores. You can use the default vmstore: or vmstores: inventory drives, or create custom drives with the New-PSDrive commandlet. Files and directories can be copied using the Copy-DatastoreItem commandlet. For more information, see the The Datastore Provider section of the vSphere PowerCLI Administration Guide.

To create a new custom PowerShell drive for a vSphere datastore:
1.Connect to an ESX/ESXi host or vCenter Server using PowerCLI:

````PowerShell
Connect-VIServer -Server ServerNameOrIPAddress
````

2.Get a datastore object:

````PowerShell
$datastore = Get-Datastore "MyDatastoreName"
````

3.Create a new PowerShell drive, such as ds:, that maps to $datastore:
````PowerShell
New-PSDrive -Location $datastore -Name ds -PSProvider VimDatastore -Root "\"
````

Acces :
````PowerShell
Set-Location ds:\ 
ls d:\ 
````
