#PowerShell

##Output format :

Format-Wide, Format-List, Format-Table

Example : Get-Process -Name powershell | Format-Wide

More here => https://technet.microsoft.com/fr-fr/library/Dd347677.aspx

##Condition : where

More here => https://technet.microsoft.com/en-us/library/hh849715.aspx

###EXAMPLE

This command gets a list of all services that are currently stopped. The "$_" symbol represents each object that is passed to the Where-Object cmdlet.

The first command uses the script block format. The second command uses the comparison statement format. The commands are equivalent and can be used interchangeably.
````Powershell

Get-Service | Where-Object {$_.Status -eq "Stopped"}
PS C:\>Get-Service | where Status -eq "Stopped"
````
