# Notes

## Useful link

**Ref list**

http://pubs.vmware.com/vsphere-60/index.jsp

https://communities.vmware.com/community/vmtn/automationtools/powercli/overview

A lot of example :

https://pubs.vmware.com/vsphere-60/index.jsp#com.vmware.powercli.ug.doc/GUID-3E36F4EA-3742-48BA-BB4B-7E0A2EAAE83E.html

https://pubs.vmware.com/vsphere-60/topic/com.vmware.ICbase/PDF/vsp_powercli_60_usg.pdf

##Reference example

Connect to vCenter Server or ESXi

```Powershell
$srv = Connect-VIServer –Server 192.168.0.10 -User Admin -Password Pass01
Disconnect-VIServer -Server $srv -Confirm:$false
```

vSwitch
```Powershell
Get-VirtualSwitch -VM (Get-VM -Name "Lync-Edge-03")
New-VirtualSwitch -VMHost (Get-VMHost -Name 192.168.0.10) -Name Switch02

$vs = New-VirtualSwitch -Host 192.168.0.10 -Name VirtSwitch
Set-VirtualSwitch -VirtualSwitch $vs -MTU 500
```

Port Group Operations

```Powershell
To list all the port groups and some of their properties:
$vs = Get-VirtualSwitch -VMHost 192.168.0.10 -Name Switch02
Get-VirtualPortGroup -VirtualSwitch $vs
To add a new port group to a virtual switch:
$vs = Get-VirtualSwitch -VMHost 192.168.0.10 -Name Switch02
$vpg = New-VirtualPortGroup -VirtualSwitch $vs -Name VPG1
Other cmdlets include:
Remove-VirtualPortGroup
Set-VirtualPortGroup
```

Managing Events Alarms

```Powershell
Get-AlarmDefinition -Name "virtual machine*" -Enabled $false

Get-VMHost hostname | Get-AlarmDefinition # Returns all alarms that
apply to the host “hostname”. Includes alarms defined on this host and
alarms inherited from the parent entity, or from any ancestors in the
inventory hierarchy.
```

###Connect

##Datacenter Operations

Info (blog) => http://pipe2text.com/?page_id=2673

```Powershell

Get-Datacenter

Move-Datacenter

New-Datacenter

Remove-Datacenter

Set-Datacenter
```

##VMware vSphere Server

```Powershell
New-Datastore
Remove-Datastore
Get-Datastore
Set-Datastore
```
