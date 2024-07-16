---
description: Removes an assignable device from a virtual machine host.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/remove-vmhostassignabledevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-VMHostAssignableDevice
---

# Remove-VMHostAssignableDevice

## SYNOPSIS
Removes a device assigned to a virtual machine (VM) host.

## SYNTAX

### Path (Default)

```
Remove-VMHostAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-InstancePath <String>] [-LocationPath <String>]
 -ResourcePoolName <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object

```
Remove-VMHostAssignableDevice [-HostAssignableDevice] <VMHostAssignableDevice[]>
 -ResourcePoolName <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-VMHostAssignableDevice` cmdlet removes a device that is assigned to a virtual machine
host. Depending on the parameters specified, you can remove devices by providing either the
instance or location path of the device.

## EXAMPLES

### Example 1

```powershell
$params = @{
InstancePath = "PCIROOT(0)#PCI(0300)#PCI(0000)"
ResourcePoolName = "MyResourcePool"
}
Remove-VMHostAssignableDevice $params
```

This example removes the device with the specified instance path from the resource pool named
**MyResourcePool**.

## PARAMETERS

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies one or more Hyper-V hosts from which the assignable devices are to be removed. NetBIOS
names, IP addresses, and fully qualified domain names are allowed. The default is the local
computer. Use localhost or a dot (`.`) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: Path
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
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

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

### -HostAssignableDevice

Specifies the device object to be removed. You can get this object using
`Get-VMHostAssignableDevice`.

```yaml
Type: VMHostAssignableDevice[]
Parameter Sets: Object
Aliases: VMHostAssignableDevice

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstancePath

Specifies the Device Instance path in the host machine.

```yaml
Type: String
Parameter Sets: Path
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
Parameter Sets: Path
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolName

Specifies the name of the resource pool from which to remove an assignable device.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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

### Microsoft.HyperV.PowerShell.VMHostAssignableDevice[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-VMHostAssignableDevice](add-vmhostassignabledevice.md)

[Get-VMHostAssignableDevice](get-vmhostassignabledevice.md)

[Dismount-VMHostAssignableDevice](dismount-vmhostassignabledevice.md)

[Mount-VMHostAssignableDevice](mount-vmhostassignabledevice.md)
