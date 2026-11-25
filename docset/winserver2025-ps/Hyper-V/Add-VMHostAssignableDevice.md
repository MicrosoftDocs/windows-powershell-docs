---
description: Assigns a device to a virtual machine host.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 06/12/2024
online version: https://learn.microsoft.com/powershell/module/hyper-v/add-vmhostassignabledevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-VMHostAssignableDevice
---

# Add-VMHostAssignableDevice

## SYNOPSIS
Adds an assignable device to a virtual machine (VM) host.

## SYNTAX

### Path (Default)

```
Add-VMHostAssignableDevice [-CimSession <CimSession[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential[]>] [-Force] [-InstancePath <String>] [-LocationPath <String>]
 -ResourcePoolName <String[]> [<CommonParameters>]
```

### Object

```
Add-VMHostAssignableDevice [-Force] [-HostAssignableDevice] <VMHostAssignableDevice[]>
 -ResourcePoolName <String[]> [<CommonParameters>]
```

## DESCRIPTION

The `Add-VMHostAssignableDevice` cmdlet assigns a hardware device to a virtual machine host. You
can add devices to the VM host by providing either the instance or location path of the device, or
by specifying an existing host-assignable device object.

## EXAMPLES

### Example 1

```powershell
$params = @{
ComputerName = "MyVM01"
InstancePath = "PCI\VEN_8086&DEV_0F48&SUBSYS_72708086&REV_0B\3&11583659&0&D8"
ResourcePoolName = "MyResourcePool"
}
Add-VMHostAssignableDevice $params
```

This example assigns a device identified by its instance path to VM host **MyVM01** within the
resource pool **MyResourcePool**.

### Example 2

```powershell
$gpu = Get-VMHostAssignableDevice
Add-VMHostAssignableDevice -HostAssignableDevice $gpu -ResourcePoolName "GpuChildPool"
```

This example retrieves a list of GPUs or other assignable devices and adds these devices to a
resource pool named **GpuChildPool**, making the devices available for use by virtual machines in
that resource pool.

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

Specifies the name of the Hyper-V host to which the device is to be added. NetBIOS names, IP
addresses, and fully qualified domain names are allowed. The default is the local computer. Use
localhost or a dot (`.`) to specify the local computer explicitly.

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

Specifies the device object to be assigned to the virtual machine.

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

### -ResourcePoolName

Specifies the name of the resource pool to which the device is assigned.

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

[Get-VMHostAssignableDevice](get-vmhostassignabledevice.md)

[Dismount-VMHostAssignableDevice](dismount-vmhostassignabledevice.md)

[Mount-VMHostAssignableDevice](mount-vmhostassignabledevice.md)

[Remove-VMHostAssignableDevice](remove-vmhostassignabledevice.md)
