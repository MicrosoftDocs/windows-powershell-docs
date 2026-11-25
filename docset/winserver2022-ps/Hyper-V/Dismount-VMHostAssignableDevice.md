---
description: Dismounts an assignable device from a virtual machine host.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/dismount-vmhostassignabledevice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Dismount-VMHostAssignableDevice
---

# Dismount-VMHostAssignableDevice

## SYNOPSIS
Dismounts a device from a virtual machine (VM) host.

## SYNTAX

```
Dismount-VMHostAssignableDevice [-InstancePath <String>] [-LocationPath <String>] [-Force]
 [-Passthru] [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Dismount-VMHostAssignableDevice` cmdlet is used to dismount an assignable device from the
virtual machine host. Use this cmdlet when you need to reassign a device or resolve conflicts
between devices and virtual machines.

## EXAMPLES

### Example 1

```powershell
Dismount-VMHostAssignableDevice -InstancePath "PCIROOT(0)#PCI(1D02)#PCI(0000)"
```

This example dismounts the device with the specified instance path from the host, making it
available for assignment to a virtual machine.

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

Specifies one or more Hyper-V hosts from which the assignable devices are to be dismounted. NetBIOS
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

Using the **Force** parameter also overrides some security checks in the platform. To learn more,
see [Dismount the device from the host partition
](/windows-server/virtualization/hyper-v/deploy/deploying-graphics-devices-using-dda#dismount-the-device-from-the-host-partition).

If no partitioning driver is provided, during dismount, you must use `-Force` to bypass the
security warning. For more information about the security implications, see [Plan for deploying devices by using Discrete Device Assignment](/windows-server/virtualization/hyper-v/plan/plan-for-deploying-devices-using-discrete-device-assignment).

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

### None

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostAssignableDevice

## NOTES

## RELATED LINKS

[Add-VMHostAssignableDevice](add-vmhostassignabledevice.md)

[Get-VMHostAssignableDevice](get-vmhostassignabledevice.md)

[Mount-VMHostAssignableDevice](mount-vmhostassignabledevice.md)

[Remove-VMHostAssignableDevice](remove-vmhostassignabledevice.md)
