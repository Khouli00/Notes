##Modifying Virtual Machines

1. Increase the Size of a VMDK File 

* Identify VM 
* Identify HD (if more than one) + change size (note: host OS should rescan size)

Simple case :

Get-HardDisk -VM $vm | Set-HardDisk -CapacityGB 80

Else :

Get-Vm virtualmachinename | Get-Harddisk | Format-List







2.	Adjust Memory Allocation on a Virtual Machine 
3.	Rename a Virtual Machine in the vCenter Server Inventory 
4.	Add and Remove a Raw LUN on a Virtual Machine 
5.	Expand a Thin-Provisioned Virtual Disk
