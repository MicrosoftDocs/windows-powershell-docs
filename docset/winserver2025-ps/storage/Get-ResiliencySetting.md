---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ResiliencySetting.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-resiliencysetting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ResiliencySetting
---

# Get-ResiliencySetting

## SYNOPSIS
Gets the resiliency settings (also known as storage layouts) available for creating virtual disks on the specified storage subsystem.

## SYNTAX

### ByName (Default)
```
Get-ResiliencySetting [-Name <String[]>] [-StoragePool <CimInstance>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Get-ResiliencySetting [-UniqueId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ResiliencySetting** cmdlet gets the resiliency settings (storage layouts) available for creating virtual disks on the specified storage subsystem.
The resiliency settings vary depending on the storage subsystem; the Windows Storage subsystem supports the Simple, Mirror, and Parity resiliency settings.

## EXAMPLES

### Example 1: Get all resiliency setting objects
```
PS C:\> Get-ResiliencySetting
Name                    NumberOfDataCopies      PhysicalDiskRedundancy  NumberOfColumns         Interleave
----                    ------------------      ----------------------  ---------------         ----------
Simple                  1                       0                       8                       65536
Mirror                  2                       1                       4                       65536
Parity                  1                       1                       8                       65536
```

This example gets all resiliency setting objects for each storage pool, showing which resiliency settings are available for use when creating virtual disks.
If there are multiple storage pools, the same resiliency setting might appear more than once, with each object representing the resiliency setting support for a particular storage pool.

### Example 2: Get only Mirror, Parity, and Simple resiliency setting objects
```
PS C:\> Get-ResiliencySetting -Name Mirror,Parity,Simple
```

This example displays only the resiliency settings for the types Mirror, Parity and Simple.
Other defined resiliency settings are not displayed.

### Example 3: Get a resiliency setting object by UniqueID
```
PS C:\>Get-ResiliencySetting -UniqueId "{5d792e9b-ca00-11e1-9350-00155db7aa01}:1"
```

This example displays one particular resiliency setting object by specifying its UniqueID value, enclosed in quotation marks.

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

### -Name
Specifies the name of the resiliency setting or settings to get.
The supported resiliency setting names vary by storage subsystem; the Windows Storage subsystem supports the following values: Simple, Mirror, or Parity.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StoragePool
Specifies the storage pool object for which to get resiliency settings.
Enter a StoragePool CIM object.
The Storage Pool CIM object is exposed by the Get-StoragePool cmdlet.

```yaml
Type: CimInstance
Parameter Sets: ByName
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
Specifies the UniqueID of the resiliency setting object to get.
If the UniqueID includes brackets, enclose the string in quotation marks.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StoragePool
You can pipe an MSFT_StoragePool object to the *StoragePool* parameter to get the resiliency setting associated with the StoragePool object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_ResiliencySetting
The Get-ResiliencySetting cmdlet returns objects representing resiliency settings for a particular storage pool.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-StoragePool](./Get-StoragePool.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Set-ResiliencySetting](./Set-ResiliencySetting.md)

[Set-StoragePool](./Set-StoragePool.md)

