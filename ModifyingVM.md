##Modifying Virtual Machines

**Note: not tested yet**

1. Increase the Size of a VMDK File 

* Identify VM 
* Identify HD (if more than one) + change size (note: host OS should rescan size)

Simple case :

````PowerShell
Get-HardDisk -VM $vm | Set-HardDisk -CapacityGB XX
````

Else :

````PowerShell
Get-Vm virtualmachinename | Get-Harddisk | Where {$_.Filename -eq $name}| Set-HardDisk -CapacityGB XX
````

2.	Adjust Memory Allocation on a Virtual Machine 

Set-VM XX -MemoryMB XX

3.	Rename a Virtual Machine in the vCenter Server Inventory 

Set-VM XX -Name XX

4.	Add and Remove a Raw LUN on a Virtual Machine 



5.	Expand a Thin-Provisioned Virtual Disk
