---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 08/30/2021
online version: https://docs.microsoft.com/powershell/module/storage/add-storagefaultdomain?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-StorageFaultDomain
---

# Add-StorageFaultDomain

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByVirtualDisk
```
Add-StorageFaultDomain [-VirtualDisk] <CimInstance> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskFriendlyName
```
Add-StorageFaultDomain -VirtualDiskFriendlyName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskName
```
Add-StorageFaultDomain -VirtualDiskName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByVirtualDiskUniqueId
```
Add-StorageFaultDomain -VirtualDiskUniqueId <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTier
```
Add-StorageFaultDomain [-StorageTier] <CimInstance> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTierFriendlyName
```
Add-StorageFaultDomain -StorageTierFriendlyName <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByStorageTierUniqueId
```
Add-StorageFaultDomain -StorageTierUniqueId <String> [-StorageFaultDomains <CimInstance[]>]
 [-StorageFaultDomainFriendlyNames <String[]>] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFaultDomainFriendlyNames
{{ Fill StorageFaultDomainFriendlyNames Description }}

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

### -StorageFaultDomains
{{ Fill StorageFaultDomains Description }}

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTier
Specifies a storage tier as a **CIMInstance** object.
The cmdlet gets the virtual disks included in the storage tier that you specify.
To obtain a virtual disk object, use the Get-StorageTier cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByStorageTier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageTierFriendlyName
{{ Fill StorageTierFriendlyName Description }}

```yaml
Type: String
Parameter Sets: ByStorageTierFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierUniqueId
{{ Fill StorageTierUniqueId Description }}

```yaml
Type: String
Parameter Sets: ByStorageTierUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

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

### -VirtualDisk
Specifies a virtual disk as a **CimInstance** object.
To obtain a virtual disk object, use the **Get-VirtualDisk** cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualDiskFriendlyName
Specifies the friendly name of the virtual disk.

```yaml
Type: String
Parameter Sets: ByVirtualDiskFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskName
Specifies the name of the virtual disk. This parameter is not equivalent to the
*VirtualDiskFriendlyName* parameter that can be set by a user.

```yaml
Type: String
Parameter Sets: ByVirtualDiskName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskUniqueId
Specifies the ID of the virtual disk.

```yaml
Type: String
Parameter Sets: ByVirtualDiskUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
