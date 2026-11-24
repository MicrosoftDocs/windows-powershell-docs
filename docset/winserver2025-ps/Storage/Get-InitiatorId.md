---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: InitiatorId.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-initiatorid?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InitiatorId
---

# Get-InitiatorId

## SYNOPSIS
Gets the InitiatorID objects for the specified iSCSI initiators.

## SYNTAX

### ByAddress (Default)
```
Get-InitiatorId [[-InitiatorAddress] <String[]>] [-HostType <HostType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-InitiatorId [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByMaskingSet
```
Get-InitiatorId [-MaskingSet <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDisk
```
Get-InitiatorId [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageSubSystem
```
Get-InitiatorId [-StorageSubSystem <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-InitiatorId** cmdlet gets the InitiatorID objects for the specified iSCSI initiators.

## EXAMPLES

### Example 1: Get all InitiatorIDs
```
PS C:\>Get-InitiatorID
```

This example gets and displays all iSCSI initiator IDs on the computer.

### Example 2: Get the storage providers for each InitiatorID
```
PS C:\>Get-InitiatorId | Get-StorageSubSystem | Get-StorageProvider
```

This example gets and displays the storage providers for each InitiatorID by piping the output from the **Get-InitiatorId** cmdlet to the **Get-StorageSubSystem** cmdlet, and then piping that cmdlet's output to the **Get-StorageProvider** cmdlet.

### Example 3:Get the InitiatorID objects for a masking set
```
PS C:\>Get-InitiatorId -MaskingSet (Get-MaskingSet -FriendlyName *EQLV1)
```

This example uses the **Get-MaskingSet** cmdlet to get the masking set with a friendly name that ends with EQLV1, and then gets all associated InitiatorID objects.

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

### -HostType
Specifies the host operating system or other host environmental factors that may influence the behavior that the storage system should have when showing a virtual disk to an initiator.
If the HostType property is blank for the object you want to get, omit this parameter.

```yaml
Type: HostType[]
Parameter Sets: ByAddress
Aliases:
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorAddress
Specifies the address of the InitiatorID object you want to get.
These are the port addresses of the hosts to which the virtual disks will be made available.

```yaml
Type: String[]
Parameter Sets: ByAddress
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSet
Gets the InitiatorID objects associated with the specified MaskingSet object.
Enter a MaskingSet CIM object, which is exposed by the Get-MaskingSet cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByMaskingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Gets the InitiatorID objects associated with the specified StorageSubsystem object.
Enter a StorageSubsystem CIM object, which is exposed by the Get-StorageSubSystem cmdlet.

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
Specifies the UniqueID(s) of the InitiatorID(s) you want to get.
Separate multiple UniqueIDs with commas, and enclose brackets in quotation marks.

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
Gets the InitiatorID objects associated with the specified VirtualDisk object.
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a MaskingSet object to the *MaskingSet* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe a StorageSubsystem object to the *StorageSubsystem* parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the *VirtualDisk* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
This cmdlet returns an object that represents an initiator ID.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Remove-InitiatorId](./Remove-InitiatorId.md)

