---
description: Retrieves information about a device assigned to a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmassignabledevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMAssignableDevice
---

# Get-VMAssignableDevice

## SYNOPSIS
Retrieves information about the assignable device from a specific virtual machine.

## SYNTAX

### VMName (Default)

```
Get-VMAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-InstancePath <String>]
 [-LocationPath <String>] [<CommonParameters>]
```

### VMObject

```
Get-VMAssignableDevice [-VM] <VirtualMachine[]> [-InstancePath <String>] [-LocationPath <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-VMAssignableDevice` cmdlet retrieves information about the assignable devices that are
associated with a specific virtual machine (VM). This cmdlet can be used to list all assignable
devices that can be attached to a VM or to retrieve details about specific devices that are already
assigned. The retrieved information can include the device's instance path, location path, and
other relevant properties.

## EXAMPLES

### Example 1

```powershell
Get-VMAssignableDevice -VMName "MyVM"
```

This example retrieves all assignable devices associated with the virtual machine named **MyVM**.

## PARAMETERS

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
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
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Retrieves one or more user accounts that have permission to perform this action. The default is the
current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
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

Specifies the location path to the assignable device

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

### -VM

Retrieves the virtual machine which a device is assigned.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Retrieves the names of the assignable devices assigned to the specified virtual machine.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

### Microsoft.HyperV.PowerShell.VirtualMachine[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMAssignedDevice

## NOTES

## RELATED LINKS

[Add-VMAssignableDevice](add-vmassignabledevice.md)

[Remove-VMAssignableDevice](remove-vmassignabledevice.md)
