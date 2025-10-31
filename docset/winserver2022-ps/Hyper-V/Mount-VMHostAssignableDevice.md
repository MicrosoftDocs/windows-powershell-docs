---
description: Mounts an assignable device to a virtual machine host.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/mount-vmhostassignabledevice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Mount-VMHostAssignableDevice
---

# Mount-VMHostAssignableDevice

## SYNOPSIS
Mounts a device to a virtual machine (VM) host.

## SYNTAX

### Path (Default)

```
Mount-VMHostAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-InstancePath <String>] [-LocationPath <String>] [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object

```
Mount-VMHostAssignableDevice [-HostAssignableDevice] <VMHostAssignableDevice[]> [-Passthru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Mount-VMHostAssignableDevice` cmdlet mounts a device such as GPUs, network adapters, or storage
controllers that are physically present on the virtual machine host.

## EXAMPLES

### Example 1

```powershell
$device = Get-VMHostAssignableDevice -InstancePath "PCIROOT(0)#PCI(0300)#PCI(0000)"
$params = @{
HostAssignableDevice = $device
VMName = "MyVM"
}
Mount-VMHostAssignableDevice @params
```

In this example, the `Get-VMHostAssignableDevice` cmdlet retrieves the device with the specified
instance path and stores it in the `$device` variable. The `Mount-VMHostAssignableDevice` cmdlet
then assigns this device to the virtual machine named **MyVM**.

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

Specifies one or more Hyper-V hosts from which the assignable devices are to be mounted. NetBIOS
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

### -HostAssignableDevice

Specifies the assignable device to be mounted on the virtual machine host.

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

Represents the Device Instance path in the host machine.

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

### Microsoft.HyperV.PowerShell.VMHostAssignableDevice

## NOTES

## RELATED LINKS

[Add-VMHostAssignableDevice](add-vmhostassignabledevice.md)

[Get-VMHostAssignableDevice](get-vmhostassignabledevice.md)

[Dismount-VMHostAssignableDevice](dismount-vmhostassignabledevice.md)

[Remove-VMHostAssignableDevice](remove-vmhostassignabledevice.md)
