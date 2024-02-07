---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MaskingSet.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/add-targetporttomaskingset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-TargetPortToMaskingSet
---

# Add-TargetPortToMaskingSet

## SYNOPSIS
Adds one or more target ports to a specified masking set, allowing a connection between the target ports, and any virtual disks and initiator IDs that the masking set contains.

## SYNTAX

### ByFriendlyName (Default)
```
Add-TargetPortToMaskingSet [-MaskingSetFriendlyName] <String[]> [-TargetPortAddresses <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByUniqueId
```
Add-TargetPortToMaskingSet -MaskingSetUniqueId <String[]> [-TargetPortAddresses <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Add-TargetPortToMaskingSet -InputObject <CimInstance[]> [-TargetPortAddresses <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-TargetPortToMaskingSet** cmdlet adds one or more target ports to a specified masking set, allowing a connection between the target ports, and any virtual disks and initiator IDs that the masking set contains.
All target ports must use the same connection type (for example iSCSI or Fibre Channel).

Note: This cmdlet works only on storage subsystems that support multi-port per view selection (MaskingPortsPerView = 3).
To view the MaskingPortsPerView property, type the following cmdlets: `Get-StorageSubSystem | Format-Table -Property FriendlyName, MaskingPortsPerView`

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Add a target port
```
PS C:\> $TargetPortObject = Get-TargetPort
PS C:\> $subSystem = Get-StorageSubSystem SANArray1
PS C:\> $maskingSet = Get-MaskingSet "Cluster1MaskingSet"
PS C:\> $subSystem | Get-TargetPort | Where-Object ConnectionType -eq "Fibre Channel" | Format-Table -AutoSize FriendlyName, PortAddress
FriendlyName          PortAddress
------------          -----------
Stor1_FCTargetPort.0a 500A098387995A75
Stor1_FCTargetPort.0b 500A098487995A75
Stor1_FCTargetPort.0c 500A098187995A75
Stor1_FCTargetPort.0d 500A098287995A75


PS C:\> $maskingSet | Add-TargetPortToMaskingSet -TargetPortAddresses "500A098187995A75"
```

This example demonstrates enumerating the Fibre Channel target ports on a given storage subsystem, and adding one of the target ports to an existing masking set.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaskingSetFriendlyName
Specifies the friendly name of the masking set to which you want to assign a target port.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSetUniqueId
Specifies the UniqueID of the masking set to which you want to assign a target port.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing the masking set to which it added target ports.
By default, this cmdlet does not generate any output.

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

### -TargetPortAddresses
Specifies one or more target port addresses, which you can view by looking at the PortAddress property returned by the Get-TargetPort cmdlet.
The target port addresses will be added to the masking set.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a MaskingSet object to the InputObject parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
If you specify the *Passthru* parameter, this cmdlet outputs an object that represents the masking set to which you added a target port.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-MaskingSet](./Get-MaskingSet.md)

[Get-TargetPort](./Get-TargetPort.md)

[New-MaskingSet](./New-MaskingSet.md)

