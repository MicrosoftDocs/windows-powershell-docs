---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MaskingSet.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-maskingset?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-MaskingSet
---

# Get-MaskingSet

## SYNOPSIS
Gets masking sets.
Masking sets are used to grant access to a virtual disk or iSCSI VHD for one or more servers.

## SYNTAX

### ByFriendlyName (Default)
```
Get-MaskingSet [[-FriendlyName] <String[]>] [-HostType <HostType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-MaskingSet [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByTargetPort
```
Get-MaskingSet [-TargetPort <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInitiatorId
```
Get-MaskingSet [-InitiatorId <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-MaskingSet [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-MaskingSet [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-MaskingSet** cmdlet returns a list of created masking sets.
Masking sets are used to grant access to a virtual disk or iSCSI VHD for one or more servers.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Get all masking sets
```
PS C:\> Get-MaskingSet
```

This example gets and displays all existing MaskingSet objects which have been created using any available Storage Management Providers across all visible storage subsystems.

### Example 2: Get all Microsoft Windows masking sets
```
PS C:\> Get-MaskingSet -HostType MicrosoftWindows
```

This example gets and displays all masking sets hosted by a computer running Microsoft Windows.

### Example 3: Get the masking set for a specific virtual disk
```
PS C:\> Get-MaskingSet -VirtualDisk (Get-VirtualDisk -FriendlyName CompanyData)
```

This example gets the masking set for the CompanyData virtual disk.
It does so by using the **Get-VirtualDisk** cmdlet to get the appropriate VirtualDisk object and provide it to the *VirtualDisk* parameter of **Get-MaskingSet**.

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

### -FriendlyName
Gets the masking set with the specified friendly name or friendly name pattern.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostType
Specifies the host operating system or other host environmental factors that may influence the behavior that the storage system should have when showing a virtual disk to an initiator.
If the HostType property is blank for the object you want to get, omit this parameter.

```yaml
Type: HostType[]
Parameter Sets: ByFriendlyName
Aliases:
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorId
Gets the masking set associated with the specified InitiatorId object.
Enter an InitiatorID CIM object, which is exposed by the Get-InitiatorId cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByInitiatorId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Gets the masking set associated with the specified StorageSubSystem object.
Enter a StorageSubSystem CIM object, which is exposed by the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetPort
Gets the masking set associated with the specified TargetPort object.
Enter a TargetPort CIM object, which is exposed by the Get-TargetPort cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByTargetPort
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -UniqueId
Specifies the UniqueID of the masking set to get.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Gets the masking set associated with the specified VirtualDisk object.
Enter a VirtualDisk CIM object, which is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
You can pipe an InitiatorId object to the *InitiatorId* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe a StorageSubsystem object to the *StorageSubsystem* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_TargetPort
You can pipe a TargetPort object to the *TargetPort* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
This cmdlet outputs an object that represents a masking set.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Get-TargetPort](./Get-TargetPort.md)

[New-MaskingSet](./New-MaskingSet.md)

[Remove-MaskingSet](./Remove-MaskingSet.md)

[Rename-MaskingSet](./Rename-MaskingSet.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

