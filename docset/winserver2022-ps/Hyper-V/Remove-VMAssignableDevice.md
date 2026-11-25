---
description: Removes a device assigned to a virtual machine.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmassignabledevice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMAssignableDevice
---

# Remove-VMAssignableDevice

## SYNOPSIS
Removes information about the assignable devices from a specific virtual machine.

## SYNTAX

### VMName (Default)

```
Remove-VMAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-VMName] <String[]> [-InstancePath <String>]
 [-LocationPath <String>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object

```
Remove-VMAssignableDevice [-VMAssignableDevice] <VMAssignedDevice[]> [-Passthru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-VMAssignableDevice` cmdlet removes an assignable device from a specified virtual
machine (VM). This is often used in scenarios where a physical device, such as a GPU or network
adapter, was previously assigned to a VM and needs to be unassigned.

## EXAMPLES

### Example 1

```powershell
$params = @{
VMName = "MyVM"
InstancePath = "PCIROOT(0)#PCI(0300)#PCI(0000)#PCI(0800)#PCI(0000)#PCI(1000)"
}
Remove-VMAssignableDevice $params
```

This example removes a specific assignable device, identified by its instance path, from the
virtual machine named **MyVM**.

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

Specifies one or more Hyper-V hosts on the virtual network adapters are to be retrieved. NetBIOS
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

Specifies one or more user accounts that have permission to perform this action. The default is the
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

Removes the Device Instance path in the host machine.

```yaml
Type: String
Parameter Sets: VMName
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
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru

Returns an object for each process that the cmdlet started.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMAssignableDevice

Specifies the assignable device object that you want to remove from the virtual machine. This is
usually an object retrieved from a cmdlet like `Get-VMAssignableDevice`.

```yaml
Type: VMAssignedDevice[]
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName

Specifies the name of the virtual machine from which you want to remove the assignable device.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.HyperV.PowerShell.VMAssignedDevice[]

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMAssignedDevice

## NOTES

## RELATED LINKS

[Add-VMAssignableDevice](add-vmassignabledevice.md)

[Get-VMAssignableDevice](get-vmassignabledevice.md)
