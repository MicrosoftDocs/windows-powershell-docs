---
description: Retrieves information about an assignable device to a virtual machine host.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmhostassignabledevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHostAssignableDevice
---

# Get-VMHostAssignableDevice

## SYNOPSIS
Retrieves device information assigned to a virtual machine (VM) host.

## SYNTAX

```
Get-VMHostAssignableDevice [-InstancePath <String>] [-LocationPath <String>]
 [-ResourcePoolName <String[]>] [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-VMHostAssignableDevice` cmdlet retrieves information about devices that can be assigned to
a virtual machine host. This can include devices such as GPUs, network adapters, or storage
controllers that are physically present on the host system. The cmdlet can filter devices by their
instance path or location path.

## EXAMPLES

### Example 1

```powershell
Get-VMHostAssignableDevice
```

This example retrieves all assignable devices on the host computer.

### Example 2

```powershell
Get-VMHostAssignableDevice -ComputerName "MyHost"
```

In this example, the cmdlet retrieves all assignable devices from the computer named **MyHost**.

## PARAMETERS

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts from which the assignable devices are to be retrieved. NetBIOS
names, IP addresses, and fully qualified domain names are allowed. The default is the local
computer. Use localhost or a dot (`.`) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstancePath

Represents the Device Instance path in the host machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocationPath

Specifies the location path to the assignable device.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName

Retrieves the name of the resource pool to which the device is assigned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostAssignableDevice

## NOTES

## RELATED LINKS

[Add-VMHostAssignableDevice](add-vmhostassignabledevice.md)

[Dismount-VMHostAssignableDevice](dismount-vmhostassignabledevice.md)

[Mount-VMHostAssignableDevice](mount-vmhostassignabledevice.md)

[Remove-VMHostAssignableDevice](remove-vmhostassignabledevice.md)
