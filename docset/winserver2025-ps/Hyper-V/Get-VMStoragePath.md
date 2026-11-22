---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmstoragepath?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMStoragePath
---

# Get-VMStoragePath

## SYNOPSIS
Gets the storage paths in a storage resource pool.

## SYNTAX

```
Get-VMStoragePath [[-Path] <String[]>] [-ResourcePoolName] <String[]> [-ResourcePoolType] <VMResourcePoolType>
 [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMStoragePath** cmdlet gets the storage paths in a storage resource pool.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMStoragePath -ResourcePoolName VHD1 -ResourcePoolType VHD
```

Gets the storage paths from virtual hard drive resource pool VHD1.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

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
Specifies one or more Hyper-V hosts on which storage paths are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

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

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

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

### -Path
Specifies the path for which matching storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool for which storage paths are to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourcePoolType
Specifies the type of the resource pool for which storage paths are to be retrieved.
Valid values are:

- Memory
- Processor
- Ethernet
- VHD
- ISO
- VFD
- FibreChannelPort
- FibreChannelConnection

```yaml
Type: VMResourcePoolType
Parameter Sets: (All)
Aliases:
Accepted values: Memory, Processor, Ethernet, VHD, ISO, VFD, FibreChannelPort, FibreChannelConnection, PciExpress

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMStorageResourcePool

## NOTES

## RELATED LINKS

